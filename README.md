# SidraApp models

Model files the SidraApp iOS app downloads at runtime. The files are attached to this repo's
releases; the repo itself holds only this README and the licence.

## Recite model (release `recite-model-v1`)

`ggml-tarteel-base-ar-quran.bin` powers Recite Mode, which follows a user's Quran recitation on
the device with [whisper.cpp](https://github.com/ggml-org/whisper.cpp). Audio never leaves the
phone.

- **Model:** [tarteel-ai/whisper-base-ar-quran](https://huggingface.co/tarteel-ai/whisper-base-ar-quran)
  by Tarteel AI, a fine-tune of OpenAI's Whisper base model for Quran recitation.
- **Licence:** Apache License 2.0, see [LICENSE](LICENSE). The weights remain the work of their
  authors.
- **Changes:** converted from the original PyTorch weights to whisper.cpp's GGML format at 16-bit
  precision. Nothing else is changed. This file is byte-identical to the conversion published at
  [B1uqa/whisper-base-ar-quran-ggml](https://huggingface.co/B1uqa/whisper-base-ar-quran-ggml/tree/2296db0027c1a01e9b75afe09821396038f1d3fa)
  (commit `2296db0`).
- **Size:** 147,951,465 bytes
- **SHA-256:** `aaebca10e2a65a6dda073a6b3ac59900f91887628acf872c565a0198ee850ead`

Download:
<https://github.com/irrelevant18/sidra-models/releases/download/recite-model-v1/ggml-tarteel-base-ar-quran.bin>

A release file is never replaced in place: a new model gets a new release tag, so every app
version keeps downloading exactly the file it was built for.
