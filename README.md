# Imam Assistant – Quran recognizer model

Files downloaded on demand by the Imam Assistant app (Settings → Speech recognition → Quran model).

| File | Source |
|---|---|
| `quran-encoder.int8.onnx`, `quran-decoder.int8.onnx`, `quran-tokens.txt` | [tarteel-ai/whisper-tiny-ar-quran](https://huggingface.co/tarteel-ai/whisper-tiny-ar-quran), exported to sherpa-onnx int8 (see `tools/quran_model` in the app repo) |
| `silero_vad.onnx` | Silero VAD, from the sherpa-onnx `asr-models` release |

Publish as release **model-v1** so the app finds them at
`https://github.com/AbedKarmi/imamassistant-models/releases/download/model-v1/<file>`.
The app checks each file's SHA-256 (see `lib/recognition/quran_model.dart`). If a file changes,
publish a new release tag and bump `QuranModel.version` / `baseUrl` in the app.

Check the license of the upstream model before publishing, and credit Tarteel.
