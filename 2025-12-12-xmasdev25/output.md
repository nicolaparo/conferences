Session Banner - Blazor’s Christmas Quest: creare da zero un videogioco 2D in C# (e salvare il Natale!)

XMAS DEV 2025

Event Sponsors

Platinum Sponsor

Gold Sponsor

Technical Sponsor

Community

Tanto tempo fa…
Dove la mia passione ebbe inizio…

Tanto tempo fa…
Ora invece…

Tanto tempo fa…
E’ molto che non creo un videogioco…

• C’è modo di unire la mia passione per la creazione di videogiochi con le

competenze che ho acquisito in questi anni?

• No, JavaScript purtroppo non è una delle mie competenze

• Blazor Interactive Server ce la può fare?

Tanto tempo fa…
Perché creare un gioco con Blazor?

• Cross platform: Mi basta avere un browser per accedere.

• Non mi serve installarlo perché è accessibile via web. Posso pure

aggiornarlo quando mi pare.

• Se proprio proprio mi serve creare un’app nativa, posso sempre

distribuirlo come applicazione ibrida (Blazor Hybrid)

• Scrivo in C# nel web

Ma prima di scrivere qualsiasi riga di codice…
Asset

E’ un qualunque elemento utilizzato per costruire un videogioco.
È tutto ciò che il gioco “usa” per mostrare, suonare o far accadere qualcosa.

Immagini: sprite,
tileset, icone,
sfondi.

Audio: musiche,
effetti sonori, voci.

Modelli 3D e
animazioni.

Testi: dialoghi,
interfacce, menu.

Dati: mappe di
livello,
configurazioni,
script.

Ma prima di scrivere qualsiasi riga di codice…
Asset > Immagini > Tilesets

Un tileset è una raccolta di piccole tessere grafiche (i tile), tutte della stessa dimensione, utilizzate per
costruire gli ambienti del gioco (pavimenti, pareti, piattaforme, prati, ecc.).

• Ogni tile è un elemento quadrato o rettangolare (per esempio 16×16 o 32×32 pixel).
•
Il livello viene costruito componendo questi elementi come pezzi di un mosaico.
• Permettono di creare scenari complessi con un numero ridotto di immagini, ottimizzando spazio e

performance.

Sono i “mattoni” che compongono il mondo di gioco.

Ma prima di scrivere qualsiasi riga di codice…
Asset > Immagini > Sprites

Gli sprite sono immagini 2D utilizzate per rappresentare personaggi, oggetti, nemici, proiettili o
qualunque elemento “mobile” all’interno del gioco.

• Sono elementi indipendenti che vengono disegnati sopra lo sfondo.
• Possono includere animazioni, costituite da più fotogrammi (ad esempio camminata, salto, attacco).
• Vengono gestiti dal motore di gioco per permettere movimenti, collisioni e cambi di stato.

Ora Scriviamo qualche riga di codice…
Scegliamo un Game Engine… ?

Non esiste un Game Engine per Blazor

Costruiamo Il nostro Game Engine

Game
la classe base per il
gioco, gestisce il game
loop e lo stato globale

GameObject
entità del gioco che
possono essere
istanziate, aggiornate e
renderizzate

GameView
il componente Razor
che collega il game loop
al rendering Canvas

Costruiamo Il nostro Game Engine

Creation

Draw

Step

Destroy

Il Rendering

RequestFrame

Canvas.Draw…()

…done…

Canvas.Draw…()

…done…

Await

Await

33ms MAX

Il Rendering

RequestFrame

Canvas.Draw…()

Canvas.Draw…()

Canvas.Draw…()

Batch

Canvas.Draw…()

Canvas.DrawBatch(batch)

Await

…done…

Canvas Library for Blazor
Blazor.Extensions.Canvas

https://github.com/BlazorExtensions/Canvas

In your index.html file (WebAssembly Apps) / _Host.cshtml (Server Apps) / App.razor file, place a
reference to the library's script file:

<script src="_content/Blazor.Extensions.Canvas/blazor.extensions.canvas.js">
</script>

In your _Imports.razor add the following using entry:

@using Blazor.Extensions.Canvas

In the component where you want to place a canvas element, add a BECanvas. Make sure to set the
ref to a field on your component:

<BECanvas Width="300" Height="400" @ref="_canvasReference" ></BECanvas>

Canvas Library for Blazor
Blazor.Extensions.Canvas

protected override async Task OnAfterRenderAsync(bool firstRender)
{

var context = await canvasReference.CreateCanvas2DAsync();

await context.BeginBatchAsync();

await context.SetFillStyleAsync("green");
await context.FillRectAsync(10, 100, 100, 100);

await context.SetFontAsync("48px serif");
await context.StrokeTextAsync("Hello Blazor!!!", 10, 100);

await context.EndBatchAsync();

}

Il Game Loop - Cuore dell'Engine – JS Interop

Il game loop è gestito da JavaScript per garantire un timing preciso con requestAnimationFrame:

export async function executeFrame(dotnetReference, callbackFunctionName) {

await dotnetReference.invokeMethodAsync(callbackFunctionName);

setTimeout(() => {

window.requestAnimationFrame(() => executeFrame(dotnetReference, callbackFunctionName));

}, 1000 / (window.fps));

};

export function setFPS(fps) {

window.fps = fps;

}

•
•
•

requestAnimationFrame sincronizza con il refresh del browser
Il setTimeout permette di limitare gli FPS (es. 60 FPS)
La chiamata asincrona a C# (invokeMethodAsync) mantiene il loop reattivo

Il Game Loop - Cuore dell'Engine – C#

Ogni frame esegue questa sequenza nel metodo ExecuteFrameAsync:

internal async Task ExecuteFrameAsync(RenderingContext context)
{

// Snapshot delle istanze (per evitare problemi di concorrenza)
var instances = this.instances.ToArray();

// FASE DI RENDERING
if (context is Canvas2DContext canvas2DContext)
{

await OnDrawAsync(canvas2DContext);
foreach (var obj in instances)

await obj.OnDrawAsync(canvas2DContext);

}

// FASE DI UPDATE
await OnStepAsync();
foreach (var obj in instances)

await obj.ExecuteStepAsync();

// Draw del Game

// Draw di ogni GameObject

// Step del Game

// Step di ogni GameObject

}

•
•

Lo snapshot ToArray() previene modifiche concorrenti durante l'iterazione
Il rendering avviene prima dell'update logico

Gestione Degli Input

Il Problema: Distinguere "Hold" da "Pressed"
Un gioco deve distinguere tra:
• Check: "Il tasto è premuto?" (tenuto premuto)
• CheckPressed: "Il tasto è stato appena premuto?" (solo il primo frame)
• CheckReleased: "Il tasto è stato appena rilasciato?"

Frame Event

1
2
3
4
5

Nothing
KeyDown Event
Nothing (hold)
Nothing (hold)
KeyUp Event

keyboardPressed["Space"] previousKeyboardPressed["Space"] CheckPressed Check
FALSE
TRUE
TRUE
TRUE
FALSE

FALSE
TRUE
TRUE
TRUE
FALSE

FALSE
TRUE
FALSE
FALSE
FALSE

FALSE
FALSE
TRUE
TRUE
TRUE

Gestione Degli Input

// Stato corrente e precedente
private readonly Dictionary<string, bool> keyboardPressed = new();
private readonly Dictionary<string, bool> previousKeyboardPressed = new();

// Aggiornamento ad ogni frame
foreach (var key in keyboardPressed.Keys)

previousKeyboardPressed[key] = keyboardPressed[key];

// Logica di rilevamento
public sealed override bool KeyboardCheckPressed(string key)
{

if (!keyboardPressed.TryGetValue(key, out bool pressed))

return false;

if (!previousKeyboardPressed.TryGetValue(key, out bool previousPressed))

return false;

// Premuto adesso ma NON nel frame precedente
return !previousPressed && pressed;

}

GameObject

public abstract class GameObject(Game game) : GameEntity(game)
{

public SpriteAsset? Sprite { get; set; }
public BoundingBox? BoundingBox { get; set; }

private float imageIndex;
public int ImageIndex { get => (int)imageIndex; set => imageIndex = value; }
public float ImageSpeed { get; set; } = 1;

public float OriginalX { get; init; }
public float OriginalY { get; init; }
public float X { get; set; }
public float Y { get; set; }
public float VSpeed { get; set; }
public float HSpeed { get; set; }
public float VAcceleration { get; set; }
public float HAcceleration { get; set; }

// ...

}

Esempio di GameObject

public class Player : GameObject
{

private readonly PlayerSpriteAsset sprite;

// Il costrutor riceve dipendenze via DI
public Player(Game game, PlayerSpriteAsset sprite) : base(game)
{

this.sprite = sprite;
Sprite = sprite;
BoundingBox = new BoundingBox(0, 0, 16, 32);

}

public override void OnCreate()
{

// Chiamato dopo l'istanziazione
ImageSpeed = 0.2f;

}

public override async ValueTask OnStepAsync()
{

// Logica di movimento
if (KeyboardCheck(KeyboardKeys.ArrowRight))

HSpeed = 2;

else if (KeyboardCheck(KeyboardKeys.ArrowLeft))

else

HSpeed = -2;

HSpeed = 0;

VAcceleration = 0.5f; // Gravità

}

}

Fisica e Collisioni

public bool IsCollidingWith(GameObject other)
{

if (BoundingBox is null || other.BoundingBox is null)

return false;

// AABB (Axis-Aligned Bounding Box) collision
return !(X + BoundingBox.X + BoundingBox.Width <= other.X + other.BoundingBox.X ||

X + BoundingBox.X >= other.X + other.BoundingBox.X + other.BoundingBox.Width ||
Y + BoundingBox.Y + BoundingBox.Height <= other.Y + other.BoundingBox.Y ||
Y + BoundingBox.Y >= other.Y + other.BoundingBox.Y + other.BoundingBox.Height);

}

Due box collidono se nessuna delle seguenti condizioni è vera:

• Box1 è completamente a sinistra di Box2

• Box1 è completamente a destra di Box2

• Box1 è completamente sopra Box2

• Box1 è completamente sotto Box2

Altre Funzioni

Funzione

IsPointEmpty(x, y)

IsPointFree(x, y)

Descrizione

Verifica se la posizione alle coordinate indicate non contiene elementi solidi.

Controlla se l’oggetto può occupare la posizione indicata, testando i quattro angoli del suo
bounding box.

IsCollidingWith<T>(out others)

Cerca collisioni con tutte le istanze di tipo T presenti nel gioco e restituisce l’elenco degli
oggetti che collidono.

IsCollidingWith(other)

Verifica se i bounding box di questo oggetto e di un altro si sovrappongono.

MoveOutsideSolid(deltaX, deltaY, resolution)

Avanza nella direzione definita dallo spostamento proposto finché non trova un punto
libero da solidi.

MoveOutsideSolid(direction, maxDistance, resolution)

Avanza lungo una direzione angolare fino a raggiungere il primo punto non solido.

MoveContactSolid(deltaX, deltaY, resolution)

Avanza gradualmente nella direzione specificata fino a toccare un’area solida, fermandosi
immediatamente prima del contatto.

MoveContactSolid(direction, maxDistance, resolution)

Avanza lungo una direzione angolare finché non incontra un solido, fermandosi al primo
punto di contatto.

Demo

Questions & Discussion

Grazie!

Nicola Paro
Solution Architect

linkedin.com/in/nicolaparo

Vote for Session - Blazor’s Christmas Quest: creare da zero un videogioco 2D in C# (e salvare il Natale!)

Please Vote for This Session

Vote online at:

https://vote.dotnetdev.it/vote/xqt335vh/10560
22
