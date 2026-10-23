# voice-recorder-models

Model files downloaded on first launch by the voice-recorder Android app. The app downloads them once and then transcribes fully offline.

Files are attached to releases, not committed to the repository.

## models-v1

| File | Size | SHA-256 |
|---|---|---|
| `ggml-base.en-q5_1.bin` | 59,721,011 bytes | `4baf70dd0d7c4247ba2b81fafd9c01005ac77c2f9ef064e00dcf195d0e2fdd2f` |

Download URL: `https://github.com/wjairplane/voice-recorder-models/releases/download/models-v1/ggml-base.en-q5_1.bin`

## Source and license

`ggml-base.en-q5_1.bin` is an unmodified copy of the file published at [ggerganov/whisper.cpp on Hugging Face](https://huggingface.co/ggerganov/whisper.cpp). It is OpenAI's Whisper `base.en` model converted to ggml format and quantized (q5_1). Whisper's model weights are released by OpenAI under the MIT License.
