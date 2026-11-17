# CallGuard: Pitch Kit

## 30-second pitch

AI can now clone a loved one's voice from a few seconds of audio, so "it sounds like them" is no longer proof. But the scam *script* hasn't changed: rush you, make you keep it secret, and demand gift cards, crypto or a verification code. CallGuard listens to the call, flags those patterns live in English, Arabic and Spanish, and tells you exactly what to do next: hang up and call back on a number you trust.

---

## 2-minute demo script

Test everything once on the real laptop and Wi-Fi before presenting. Use Chrome.

| Time | You say | You do |
|---|---|---|
| 0:00 | "Imagine your grandmother gets a call. It's her grandson's voice, crying, saying he's been arrested. The voice is a clone." | Show the title slide or the CallGuard page. |
| 0:15 | "The voice can be faked. The script can't change much. That's what CallGuard watches." | Click **Grandparent scam**. |
| 0:25 | "Score 100, red. Every point is explained: urgency, secrecy, gift cards, plus a combo bonus for emergency plus untraceable payment." | Point to the gauge, the flags, and the phone turning red with the action line. |
| 0:45 | "It's not all-or-nothing. A call that only asks for a card number lands in amber: caution." | Click **Courier fee (caution)**. Point to the amber phone. |
| 1:00 | "And a normal call stays quiet, no false alarm." | Click **Normal call**. Green, score 0. |
| 1:10 | "Scams don't only happen in English." | Click **عربي**, then **Español**. Both go red. |
| 1:30 | "Now live." Choose English, click **Start listening**, read the grandparent scam aloud (or play it from your phone). | Waveform moves with your real voice; the score climbs as captions appear. |
| 1:50 | "Before anyone acts, CallGuard walks them through verification: call back on a saved number, safe word, never read out codes." | Tick the checklist; the green banner appears. |
| 2:00 | "To be clear: this reads the words, not the voice. Detecting synthetic audio is our next step, and the architecture is ready for it." | Close on the roadmap slide. |

**Backup plan:** record a 60-second screen capture of the demo in case the microphone or Wi-Fi fails. The sample buttons work with no mic and no internet (fonts aside).

---

## Slide outline (7 slides)

1. **Title**: CallGuard, one-line promise, team names, track name.
2. **The problem**: voice-clone scams are rising. *Add one stat with a source. Do not use a number you cannot cite.* Show the "grandparent scam" story in two lines.
3. **Insight**: the voice can be faked, the script can't. Four recurring signals: urgency, secrecy, untraceable payment, credential requests.
4. **Solution and live demo**: screenshot of the phone UI in red, amber and green. Then switch to the live page.
5. **How it works**: mic, speech-to-text, weighted categories + combo bonuses, three-tier verdict + next step. Mention three languages and explainable scoring.
6. **Honest limits and roadmap**: rule-based, not acoustic. Next: audio anti-spoofing model, more languages, call-flow integration. Judges respect honesty about scope.
7. **Impact and close**: who benefits (older adults, families, banks, telecoms), how it could deploy (browser extension, phone app, carrier call screening), and a one-line call to action.

---

## Likely judge questions

**Is this real AI detection?**
The transcript analysis is rule-based by design: it is transparent, instant and runs offline-capable on any device. Acoustic deepfake detection needs a trained audio model, which we scoped as the next milestone rather than faking it.

**Why rules instead of machine learning?**
Explainability and speed. For a safety warning, a person needs to see *why* it fired ("secrecy + gift cards"), and a rule engine needs no training data, no server and no latency. The same scoring output could later be blended with an ML score.

**What about false positives and evasion?**
Single weak words stay in the Low tier; it takes several signals or one very strong one (like asking for a verification code) to raise a warning. Scammers can rephrase, so the phrase lists are meant to be extended continuously, and the checklist works whatever the score says.

**What about privacy?**
Scoring runs locally; CallGuard stores and uploads nothing. The browser's speech recognition may use the vendor's cloud service, which we disclose in the app, and users can paste text instead.

**How would this actually reach people?**
Start as a web app and browser extension, then a mobile call-screening app, and ultimately carrier or bank integrations. The scoring engine is a single dependency-free function, so it ports easily.

**What did you build in the hackathon?**
The full app: multilingual weighted detection with combos, live mic captions, explainable UI, verification checklist, and the demo scenarios.
