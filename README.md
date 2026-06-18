# Language Translation Tool

A simple browser-based translator. Enter text, pick a source and target language, and get an instant translation — with copy and text-to-speech support.

## Features
- Text input with live character counter
- Source and target language dropdowns (25+ languages) with a one-click swap
- Real-time translation via a free public API (no sign-up or key needed)
- Copy-to-clipboard and listen (text-to-speech) for the translated result
- Warning notice if you select a non-Latin-script language (e.g. Telugu, Hindi) but type using English letters, since translation APIs need the actual native script to work correctly

## Tech Used
- HTML, CSS, and vanilla JavaScript — single file, no build step or installation
- [MyMemory Translation API](https://mymemory.translated.net/) for translation
- Browser's built-in `SpeechSynthesis` API for text-to-speech

## How to Run
Opening `index.html` by double-clicking can fail in some browsers (you'll see "Failed to fetch") because of local-file security restrictions. To avoid that, serve it from a local server instead:

1. Open a terminal in the project folder.
2. Run: `python -m http.server 8000` (use `python3` on Mac/Linux if needed).
3. Open `http://localhost:8000/index.html` in your browser.

## Notes & Limitations
- The free API has a daily usage quota; heavy testing may occasionally trigger a quota message.
- Romanized/phonetic text (e.g. Telugu typed in English letters) won't translate correctly — type in the actual script of the source language.
- Text-to-speech voice availability depends on your browser/OS.

## Upgrading to Google Cloud Translation or Microsoft Translator
To use an official paid API instead, only the `translateText()` function in the script needs to change — swap the MyMemory request for a call to your provider of choice, sending your API key in the request. Everything else (UI, language list, copy/speech features) stays the same.