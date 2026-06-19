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
- [ ] Higgsfield-Verbindung aktiv (aktuell vom Connector blockiert)
- [ ] Keyframes generiert
- [ ] Test-Szene animiert

> Hinweis: Generierung ist aktuell blockiert, weil die Higgsfield-Verbindung jeden
> Aufruf abweist. Sobald die Integration neu verbunden ist (und Guthaben vorhanden),
> wird die Test-Szene Shot für Shot umgesetzt.
