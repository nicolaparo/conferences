# Xmasdev25

## Main Topics Covered
- Session Banner - Blazor’s Christmas Quest: creare da zero un videogioco 2D in C# (e salvare il Natale!)
- Event Sponsors
- Community
- Tanto tempo fa…
- Dove la mia passione ebbe inizio…
- Ora invece…

## Key Takeaways and Conclusions
- public class Player : GameObject { private readonly PlayerSpriteAsset sprite; // Il costrutor riceve dipendenze via DI public Player(Game game, PlayerSpriteAsset sprite) : base(game) { this.sprite = sprite; Sprite = sprite; BoundingBox = new BoundingBox(0, 0, 16, 32); } public override void OnCreate() { // Chiamato dopo l'istanziazione ImageSpeed = 0.2f; } public override async ValueTask OnStepAsync() { // Logica di movimento if (KeyboardCheck(KeyboardKeys.ArrowRight)) HSpeed = 2; else if (KeyboardCheck(KeyboardKeys.ArrowLeft)) HSpeed = -2; else HSpeed = 0; VAcceleration = 0.5f; // Gravità } }

## Notes
- Event folder: 2025-12-12-xmasdev25
- Source deck: xmasdev2025_1056022_Paro.pptx
- Date: 2025-12-12
