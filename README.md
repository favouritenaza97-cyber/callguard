# CallGuard 🛡️

**A scam and voice-clone call screener that runs entirely in your browser.**

Live demo: `https://YOUR-USERNAME.github.io/callguard/` *(replace after enabling GitHub Pages)*

Built for the **Public Safety / AI-Powered Threat Detection** track.

---

## The problem

Voice-cloning tools make "Grandma, it's me, I'm in trouble" calls sound convincing. The *voice* can be faked, but the *script* a scammer needs rarely changes: urgency, secrecy, untraceable payment, and requests for codes or remote access.

CallGuard listens for that script and warns the person on the call, in real time, in the language they are speaking.

> TODO: add one local statistic about phone/voice scams here, with a source link.

## What it does

- **Live captions** from the microphone (Web Speech API), scored as the call happens
- **12 scam-signal categories** in **English, Arabic and Spanish**
- **Weighted 0-100 risk score** with **combo bonuses** (for example emergency + gift cards)
- **Explainable**: every point is traced to the exact phrase that triggered it
- **Three-tier phone UI**: Low (green), Caution (amber), High (red) with a plain-language next step
- **Verify-before-you-act checklist**: call back on a saved number, safe word, unscripted question, never read out codes, refuse gift cards/crypto/wires
- **Real microphone level** drives the waveform while listening
- **Sample calls** to demo every state without a microphone

## How scoring works

Each category counts **once** per call, however many times it appears.

| Category | Weight |
|---|---|
| Code / credential request | 35 |
| Secrecy | 25 |
| Payment method (gift cards, crypto, wire) | 25 |
| Remote access (AnyDesk, TeamViewer) | 25 |
| Verify resistance ("don't hang up") | 20 |
| Urgency | 15 |
| Fear / crisis | 15 |
| Authority claim (bank, police, tax) | 15 |
| Account threat | 15 |
| Prize / refund | 15 |
| ID pressure ("it's me") | 10 |
| Money amount | 10 |

**Combo bonuses** (+10 to +15) apply when two signals appear together, such as crisis + payment, authority + code request, or secrecy + urgency.

**Tiers:** 0-29 Low, 30-59 Caution, 60-100 High (score is capped at 100).

Single weak words (like "hospital") stay in the Low tier on their own. It takes several signals, or one very strong one, to raise the alarm.

## Run it

No build step and no dependencies.

1. Open `index.html` in a browser, **or** enable GitHub Pages (Settings, Pages, branch `main`, folder `/ (root)`).
2. For microphone input use Chrome, Edge or Safari. The page must be served over **HTTPS or localhost** (GitHub Pages is fine).

## Privacy

Scoring runs locally in the page. CallGuard stores nothing and uploads nothing. Note that browser speech recognition itself may send audio to the browser vendor's speech service (this is the case in Chrome and Edge). You can skip the microphone and paste or type a transcript instead.

## Limitations (please read)

- **Rule-based, not a trained model.** Scammers can rephrase to avoid the patterns, and honest callers can occasionally trigger them. A low score is not proof a call is safe; a high score is a warning, not a verdict.
- **No acoustic deepfake detection.** CallGuard analyses *what is said*, not *how the voice sounds*. Detecting a synthetic voice needs a trained audio model and is future work.
- Speech-to-text accuracy varies by browser, accent and language.
- Phrase lists are hand-written starting points, not exhaustive.

## Roadmap

- Acoustic anti-spoofing classifier (trained on ASVspoof-style data) running in the browser
- More languages and dialects, with community-maintained phrase lists
- A caller-verification handshake (safe-word challenge) built into the call flow
- Mobile app / OS call-screening integration, plus one-tap reporting to authorities

## Tech

HTML, CSS, vanilla JavaScript, Web Speech API, Web Audio API. Single file, no backend.

## Files

```
index.html   the whole app
README.md    this file
PITCH.md     demo script, slide outline, judge Q&A
```

## Team

> TODO: add team member names and roles.

## License

> TODO: choose a license (MIT is a common choice for hackathon projects).
