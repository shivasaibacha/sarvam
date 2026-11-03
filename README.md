# Read-Aloud Fluency Coach

A voice-first reading coach built on the Sarvam stack. A child reads a passage aloud, the app finds the slips, and plays back the correct pronunciation.

## How it works
- **Saaras** (speech-to-text) transcribes the reading.
- The transcript is aligned word by word against the passage. Each word is marked correct, mispronounced or skipped, and accuracy and words correct per minute (WCPM) are calculated.
- **Bulbul** (text-to-speech) plays the correct pronunciation of any word or the full passage.
- **Sarvam-105B** writes short practice sentences using the words the reader struggled with.
- Built-in passages in English, Hindi and Marathi, plus paste-your-own text.

## Run it
It is a single static file with no build step.

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Open **Settings**, paste your Sarvam API key, and start reading. Without a key, use **Try demo reading** to see the full flow.

## Deploy on GitHub Pages
Repo **Settings → Pages → Deploy from a branch → `main` / root**.

## Notes
- Your API key stays in your browser (sessionStorage) and is only sent to the Base URL in Settings. Never commit a key.
- If the browser blocks calls to `api.sarvam.ai` (CORS), point the Base URL at a small proxy that adds your key server-side.
- Model names (`saaras:v3`, `bulbul:v3`, `sarvam-105b`) and the speaker are editable in Settings.

## Roadmap
- Phoneme-level feedback
- More languages and a passage library
- Per-learner progress saved across sessions

## License
MIT
