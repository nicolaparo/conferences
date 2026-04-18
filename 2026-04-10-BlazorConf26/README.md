# BlazorConf26

## Main Topics Covered
- Videogames e Collaborative Apps: è possibile con Blazor?
- Nicola Paro
- Un grazie agli sponsor e alle community
- Applicazioni Collaborative
- Client
- Backend

## Key Takeaways and Conclusions
- public class Player : GameObject { private readonly PlayerSpriteAsset sprite; // Il costrutor riceve dipendenze via DI public Player(Game game, PlayerSpriteAsset sprite) : base(game) { this.sprite = sprite; Sprite = sprite; BoundingBox = new BoundingBox(0, 0, 16, 32); } public override void OnCreate() { // Chiamato dopo l'istanziazione ImageSpeed = 0.2f; } public override async ValueTask OnStepAsync() { // Logica di movimento if (KeyboardCheck(KeyboardKeys.ArrowRight)) HSpeed = 2; else if (KeyboardCheck(KeyboardKeys.ArrowLeft)) HSpeed = -2; else HSpeed = 0; VAcceleration = 0.5f; // Gravità } }

## Notes
- Event folder: 2026-04-10-BlazorConf26
- Source deck: presentation.pptx
- Date: 2026-04-10
