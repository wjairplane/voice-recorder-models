# voice-recorder-models

Model files downloaded on first launch by the voice-recorder Android app. The app downloads them once and then transcribes fully offline.

Files are committed to this repository, one folder per model version. Files over GitHub's 100 MB limit are attached to the release with the same name as the folder instead (tag `models-v1`). Never change a file or release asset in place: add a new version instead, so older app versions keep working.

## models-v1

| File | Where | Size | SHA-256 |
|---|---|---|---|
| `ggml-base.en-q5_1.bin` (standard) | `models-v1/` in this repo | 59,721,011 bytes | `4baf70dd0d7c4247ba2b81fafd9c01005ac77c2f9ef064e00dcf195d0e2fdd2f` |
| `ggml-small.en-q5_1.bin` (high accuracy, optional) | Release `models-v1` | 190,098,681 bytes | `bfdff4894dcb76bbf647d56263ea2a96645423f1669176f4844a1bf8e478ad30` |

Download URLs:

- `https://raw.githubusercontent.com/wjairplane/voice-recorder-models/main/models-v1/ggml-base.en-q5_1.bin`
- `https://github.com/wjairplane/voice-recorder-models/releases/download/models-v1/ggml-small.en-q5_1.bin`

## Source and license

Both files are unmodified copies of the files published at [ggerganov/whisper.cpp on Hugging Face](https://huggingface.co/ggerganov/whisper.cpp). They are OpenAI's Whisper `base.en` and `small.en` models converted to ggml format and quantized (q5_1). Whisper's model weights are released by OpenAI under the MIT License.
