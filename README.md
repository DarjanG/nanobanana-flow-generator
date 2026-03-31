# Nano Banana Flow Generator

AI sistem za masovno generisanje Facebook/Instagram story reklama koriscenjem Google Flow platforme i Claude Code automatizacije.

## Sta radi?

Dajes Claude-u link sajta klijenta + link Flow projekta, i on:
1. Procita sajt — izvuce proizvod, cene, benefite, testimonijale, stil
2. Napise 50 prodajnih promptova prilagodjenih tom proizvodu
3. Otvori Flow u Chrome-u i automatski salje promptove jedan za drugim
4. Slike se generisu u pozadini (~30 sec po slici)

## Setup (jednom)

### 1. Claude Code CLI
```bash
# Instaliraj Claude Code
npm install -g @anthropic-ai/claude-code

# Proveri da radi
claude --version
```
Treba ti Anthropic nalog sa aktivnim planom (Pro/Team).

### 2. Chrome ekstenzija "Claude in Chrome"
1. Otvori Chrome
2. Idi na Chrome Web Store
3. Pretrazi "Claude in Chrome" (od Anthropic)
4. Instaliraj ekstenziju
5. Uloguj se sa istim Anthropic nalogom

Ova ekstenzija je KLJUCNA — ona daje Claude-u pristup browser-u (klikovi, kucanje, citanje stranice).

### 3. Google nalog
- Uloguj se na https://labs.google/fx/tools/flow/ sa Google nalogom
- Besplatno je, nema API kljuceva

## Koriscenje

```bash
# Kloniraj/preuzmi ovaj folder
cd nanobanana-flow-generator

# Pokreni Claude Code u ovom folderu
claude
```

Claude automatski cita `CLAUDE.md` fajl koji mu objasnjava ceo workflow.

### Primer komande:

```
Procitaj sajt https://example.com i napravi 50 FB story vizuala (9:16).
Salje ih ovde: https://labs.google/fx/tools/flow/project/TVOJ-PROJECT-ID
```

### Pre toga napravi Flow projekat:
1. Idi na https://labs.google/fx/tools/flow/
2. Klikni "New Project" (+)
3. (Opciono) Uploaduj referentne slike — logo proizvoda, foto pakovanja
4. Kopiraj URL projekta iz browser-a
5. Daj taj URL Claude-u

## Napomene

- Flow je besplatan ali ima soft limit na generisanje (obicno 200+ slika radi bez problema)
- Tekst na slikama je AI-generisan i ponekad pogresan — za finalne reklame dodaj tekst u Canva/Photoshop
- Ako Chrome MCP veza pukne tokom sesije, samo reci "nastavi" i Claude ce se ponovo povezati
- Promptovi su na engleskom jer Nano Banana bolje razume engleski, ali tekst overlay moze biti na bilo kom jeziku
