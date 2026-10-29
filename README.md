# SidraApp models

Model files the SidraApp iOS app downloads at runtime. The files are attached to this repo's
releases; the repo itself holds only this README and the licence.

## Recite model

Recite Mode follows a user's Quran recitation on the device with
[whisper.cpp](https://github.com/ggml-org/whisper.cpp). Audio never leaves the phone.

- **Model:** [tarteel-ai/whisper-base-ar-quran](https://huggingface.co/tarteel-ai/whisper-base-ar-quran)
  by Tarteel AI, a fine-tune of OpenAI's Whisper base model for Quran recitation.
- **Licence:** Apache License 2.0, see [LICENSE](LICENSE). The weights remain the work of their
  authors.
- **Conversion:** Tarteel's PyTorch weights (commit `5c3c53fdf9272c4f6ee0bee09a1e5a4a615ee25c`)
  converted with whisper.cpp's `models/convert-h5-to-ggml.py`, with the header's `n_text_ctx` set
  to 448 (the script writes 1024, which whisper.cpp refuses to load). Nothing else is changed. The
  result is byte-identical to the conversion published at
  [B1uqa/whisper-base-ar-quran-ggml](https://huggingface.co/B1uqa/whisper-base-ar-quran-ggml/tree/2296db0027c1a01e9b75afe09821396038f1d3fa).

| Release                | File                                  | Format                                         | Bytes       |
| ---------------------- | ------------------------------------- | ---------------------------------------------- | ----------- |
| `recite-model-v1`      | `ggml-tarteel-base-ar-quran.bin`      | GGML f16                                       | 147,951,465 |
| `recite-model-q8_0-v1` | `ggml-tarteel-base-ar-quran-q8_0.bin` | the f16 quantized with `whisper-quantize q8_0` | 81,768,585  |

SHA-256:

- `ggml-tarteel-base-ar-quran.bin`: `aaebca10e2a65a6dda073a6b3ac59900f91887628acf872c565a0198ee850ead`
- `ggml-tarteel-base-ar-quran-q8_0.bin`: `72194195f7d280adebec57acf2c6e01e209484322ec1cec21c275a3c0b1e3d77`

Download links:

- <https://github.com/irrelevant18/sidra-models/releases/download/recite-model-v1/ggml-tarteel-base-ar-quran.bin>
- <https://github.com/irrelevant18/sidra-models/releases/download/recite-model-q8_0-v1/ggml-tarteel-base-ar-quran-q8_0.bin>

A release file is never replaced in place: a new model gets a new release tag, so every app
version keeps downloading exactly the file it was built for.
