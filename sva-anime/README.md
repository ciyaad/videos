# SV Anadolu Limburg — Anime Cinematic Serie

Konzept: Die Mannschaft von **SV Anadolu Limburg** wird im Stil eines epischen
Anime-Cinematics als **osmanisches Heer im Mittelalter** dargestellt, das sich auf
eine große Schlacht gegen die Feinde vorbereitet. Stil und Format orientieren sich
am viralen Referenzvideo (@deepvaultai, „AI Anime Battle / World Cup"):

- **Stil:** Japanischer Anime-Cinematic-Look, cel-shaded, filmisch, dramatisches Licht
- **Format:** Hochformat 9:16 (Reel/TikTok), Szenen à ca. 5–8 Sekunden
- **Setting:** Mittelalterliches osmanisches Heerlager, Zelte, Banner, Lagerfeuer, Dämmerung/Nacht
- **Figuren:**
  - **Heerführer / Feldherr** — Sercan Selcuk Kaya (`assets/heerfuehrer-sercan.jpeg`), Anführer des Heeres
  - **Krieger** — SVA-Spieler, Rüstung/Helme **über** dem grau-weißen SVA-Trikot, SVA-Wappen auf Bannern und Schilden
- **Dialoge:** gesprochen **Japanisch** (Anime-Voiceover) mit **deutschen Untertiteln**, epische Erzählerstimme
- **Gesichter:** Charakter-Referenz aus dem Teamfoto (`assets/team.png`), dem Heerführer-Porträt (`assets/heerfuehrer-sercan.jpeg`) + Wappen (`assets/logo.jpeg`)

## Pipeline (mit Higgsfield)

1. **Referenz hochladen** — Teamfoto + Wappen via `media_upload`
2. **Keyframe-Bilder** je Shot generieren (anime image, Gesicht als Referenz)
3. **Animation** — image-to-video je Keyframe (5–8 s)
4. **Schnitt** — Shots aneinanderhängen, Untertitel + Musik/Voiceover
5. **Export** — 9:16 Reel

## Status

- [x] Konzept & Storyboard (siehe `scenes/scene-01-lager.md`)
- [x] Higgsfield-Verbindung aktiv
- [x] Test-Keyframe generiert (Shot 3 — Heerführer, Gesichts-Referenz) → `output/test/shot3-heerfuehrer-keyframe.png`
- [x] Test-Szene animiert (5 s, 9:16, image-to-video) → `output/test/shot3-heerfuehrer-test.mp4`
- [ ] Restliche Shots (1, 2, 4) als Keyframes + Animation
- [ ] Schnitt, japanisches Voiceover + deutsche Untertitel, Musik

## Test-Ergebnis (Shot 3)

Pipeline-Test erfolgreich end-to-end durchgelaufen:

1. **Referenz** — `heerfuehrer-sercan.jpeg` + `logo.jpeg` via URL-Import nach Higgsfield.
2. **Keyframe** — `nano_banana_2` (Nano Banana Pro), 9:16, Gesicht/Bart von Sercan
   erkennbar in Anime-Cinematic-Stil übernommen.
3. **Animation** — `kling3_0_turbo`, image-to-video, 5 s, 720p, langsamer Heldenshot-Push.

> Bekannter Punkt für die finale Version: Das KI-generierte Wappen liest „SUB" statt
> „SVA". Fix: Wappen-Text per Prompt erzwingen oder das echte `logo.jpeg` im Schnitt
> als Overlay einsetzen.
