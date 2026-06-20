# SV Anadolu — Anime Cinematic Reel

Die Mannschaft von **SV Anadolu** als epische **osmanisch-türkische Eliteeinheit**,
die sich im Heerlager vor der Schlacht sammelt. Hochwertiger, halb-realistischer
Anime-Look im Stil des viralen Referenzvideos (@deepvaultai / „AnimeBlip"). Keine
Fußball-Elemente, kein modernes Setting.

- **Stil:** halb-realistischer Anime (cel-shaded, erkennbare echte Gesichter), osmanisch-türkische Rüstungen, rote/goldene Akzente, Fackeln, Banner, Staub, dramatisches Licht
- **Format:** Hochformat 9:16 (Reel/TikTok)
- **Sprache:** Dialog **gesprochen Japanisch** (Kling-eigener Lippensync) mit **deutschen Untertiteln** (nur bei gesprochenen Sätzen)
- **Ton:** keine Erzählerstimme, keine Handlungstexte; nur Naturgeräusche (Wind, Feuer, Rüstung) — **Musik erst ab der Heerführer-Ansage**

## Aktueller Stand

**Endfassung: [`output/sva-anadolu-anime-v3.mp4`](output/sva-anadolu-anime-v3.mp4)** (~46 s, 9:16)

- [x] Konzept & Storyboard (`scenes/scene-01-lager.md`)
- [x] Higgsfield-Pipeline aktiv, Stil + Lippensync bestätigt
- [x] Alle Spielerfotos importiert (6 von 7 + Heerführer)
- [x] Zwei-Personen-Gespräche (Schuss-Gegenschuss) animiert
- [x] Kompletter Schnitt mit Crossfade-Übergängen, Tonbrücke, Musik-Einsatz spät
- [ ] **Abdi & Hakan** als eigene Sprecher (Fotos fehlen noch)
- [ ] Echtes **Logo-Overlay** statt KI-Wappen (liest teils „SUA"/„SUB")
- [ ] Optional: separate Nahaufnahmen pro Sprecher (echter Kamerawechsel)

## Figuren & Gesichts-Referenzen

Heerführer = **Sercan / „selcuk11"**. Spieler = Krieger.

| Rolle | Name | Foto / Higgsfield media_id |
|---|---|---|
| Heerführer | Sercan (selcuk11) | `assets/heerfuehrer-sercan.jpeg` · `1a59837f-bb0d-4e18-9bf1-34e648dfb93b` |
| Krieger | **Ciyo** = Cihad | `cihad4.jfif` · `273df882-5b04-4776-8de9-0a992374d267` |
| Krieger | **Furki** = Furkan | `furkan3.jpeg` · `e90bd97d-a278-45ba-98e4-b1d5ddbf4228` |
| Krieger | **Musti** | `musti2.jpeg` · `2cd2cfde-6c49-45e2-9822-5bccb348d9a2` |
| Krieger | **Muro** | `muro.webp` · `ee608af3-9bea-4a55-b2c4-e3720acff9b7` |
| Krieger | **Voli** | `voli.webp` · `06b1fe81-96ce-4058-b9fa-43e9a8a77100` |
| Krieger | **Abdi** | _Foto fehlt — noch hochladen_ |
| Krieger | **Hakan** | _Foto fehlt — noch hochladen_ |
| Wappen | SV Anadolu | `assets/logo.jpeg` · `dc25694b-62a6-4cb7-9849-48ac2754546d` |

> Hinweis: media_ids gelten für den aktuellen Higgsfield-Workspace. Bei neuem
> Workspace die Assets neu importieren (Repo ist public → URL-Import möglich).

## Schnitt-Aufbau v3 (~46 s)

| # | Szene | Spieler | Gesprochen (JP) → Untertitel (DE) |
|---|---|---|---|
| 1 | Heerlager bei Nacht (Establishing) | — | nur Naturgeräusche |
| 2 | Gespräch am Feuer | **Furki → Ciyo** | 今年は誰にも負けない！ → „Dieses Jahr besiegt uns keiner." |
| 3 | …Gegenschnitt | **Ciyo → Furki** | アナドルの強さを見せてやる。 → „Jeder merkt, wer Anadolu ist." |
| 4 | Gespräch am Feuer | **Musti → Muro** | 全員、叩きのめす！ → „Wir schlagen sie alle." |
| 5 | …Gegenschnitt | **Muro → Musti** | 敵は皆、倒れる。 → „Jeder Gegner fällt." |
| 6 | Am Banner | **Voli** | アナドルは止められない。 → „Keiner stoppt Anadolu." |
| 7 | Schwur (Hände auf dem Wappen) | alle | 今年はアナドルのものだ！ → „Dieses Jahr gehört Anadolu." |
| 8 | Das Horn der Feinde | — | nur Horn/Wind |
| 9 | Heerführer tritt hervor | Sercan | — |
| 10 | Ansage (**Musik startet**) | Sercan | 今年、我らの名が知れ渡る。 → „Dieses Jahr kennt man unsere Namen." |
| 11 | Der Ruf (Klimax) | Sercan | アナドルのために！ → **„Für Anadolu!"** |

## Pipeline (Higgsfield + ffmpeg)

| Schritt | Modell / Tool | Parameter |
|---|---|---|
| Referenz-Import | `media_import_url` (public Raw-URL) bzw. Upload-Widget | Gesichter + Wappen |
| Keyframe | `nano_banana_2` (Nano Banana Pro) | 9:16, halb-realistischer Anime, Gesichts-/Wappen-Referenz |
| Animation + Stimme | `kling3_0` (mode std, **sound: on**) | image-to-video, 5 s, 720p, 9:16 — **Kling erzeugt lippensynchrone Stimme**, gesprochene Zeile steht im Prompt |
| Musik | `sonilo_music` | epische Taiko/Orchester-Spur (~32 s) |
| Schnitt | ffmpeg | `xfade`/`acrossfade` (Crossfade-Flow), `drawtext` (DE-Untertitel, Schrift Arial Bold), Musik via `adelay` ab Ansage |

**Wichtige Erkenntnis:** Lippensync kommt aus **Kling 3.0 selbst** (`sound: on`, gesprochene
Zeile im Prompt). Separat erzeugte TTS (`text2speech_v2_*`) klang zu weich und war nicht
synchron — wird nicht mehr verwendet (Reste liegen noch unter `output/test/voiceover-*`).

## Datei-Übersicht

```
sva-anime/
  README.md                         dieses Dokument
  assets/                           Eingangs-Fotos + Wappen
  scenes/scene-01-lager.md          Original-Storyboard
  output/
    sva-anadolu-anime-v3.mp4        >>> aktuelle Endfassung <<<
    sva-anadolu-anime-v2.mp4        Vorgänger (11 Einzel-Shots, kein Zwei-Personen-Dialog)
    sva-anadolu-anime.mp4           erste 6-Szenen-Fassung
    test/
      scenes/
        c-furki/c-ciyo/c-musti/c-muro/c-voli.mp4   Zwei-Personen-Gesprächsclips (v3)
        kf-furkiciyo / kf-mustimuro / kf-*.png      Keyframes
        s1..s6.mp4, d-*.mp4                          Einzel-Shots & frühere Dialog-Clips
        music32.m4a                                 Musikspur (32 s)
      shot3-*.mp4 / roar-*.mp4 / voiceover-*         frühere Shot-3-Tests
```

## Nächste Schritte

1. Fotos von **Abdi** & **Hakan** hochladen → je ein Gesprächs-/Sprech-Shot.
2. Echtes `logo.jpeg` als sauberes Overlay auf die Banner legen (Wappen-Fix).
3. Optional: pro Sprecher echte Einzel-Nahaufnahme (separater Kamerawinkel) für noch
   filmischeren Schuss-Gegenschuss.
