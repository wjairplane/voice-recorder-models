# voice-recorder-models

Model files downloaded on first launch by the voice-recorder Android app. The app downloads them once and then transcribes fully offline.

Files are committed to this repository, one folder per model version. Files over GitHub's 100 MB limit are attached to the release with the same name as the folder instead (tag `models-v1`). Never change a file or release asset in place: add a new version instead, so older app versions keep working.

## models-v1

| File | Where | Size | SHA-256 |
|---|---|---|---|
| `ggml-base.en-q5_1.bin` (standard) | `models-v1/` in this repo | 59,721,011 bytes | `4baf70dd0d7c4247ba2b81fafd9c01005ac77c2f9ef064e00dcf195d0e2fdd2f` |
| `ggml-small.en-q5_1.bin` (high accuracy, optional) | Release `models-v1` | 190,098,681 bytes | `bfdff4894dcb76bbf647d56263ea2a96645423f1669176f4844a1bf8e478ad30` |
| `nemo-fastconformer-en-480ms-encoder.int8.onnx` (live text) | Release `models-v1` | 131,507,603 bytes | `100c5616929a131b5b3c8c8ab0d83aaba2cdcae163acd8d190b4e5ffa5f7d051` |
| `nemo-fastconformer-en-480ms-decoder.int8.onnx` (live text) | Release `models-v1` | 3,955,864 bytes | `4f04431988472f8c7b815f942aa6901976929c9e22353029681fcdb262da0164` |
| `nemo-fastconformer-en-480ms-joiner.int8.onnx` (live text) | Release `models-v1` | 1,408,182 bytes | `d2d8e7290a6a8245a83ed211aa0dd8cdf8effb8a7c64fe392399561111b52f30` |
| `nemo-fastconformer-en-480ms-tokens.txt` (live text) | Release `models-v1` | 11,896 bytes | `618dc110fc2213886b52e063ff42329bbdf37a266ca7705184090fa5f39f3131` |

Download URLs:

- `https://raw.githubusercontent.com/wjairplane/voice-recorder-models/main/models-v1/ggml-base.en-q5_1.bin`
- `https://github.com/wjairplane/voice-recorder-models/releases/download/models-v1/ggml-small.en-q5_1.bin`
- `https://github.com/wjairplane/voice-recorder-models/releases/download/models-v1/nemo-fastconformer-en-480ms-<part>` for the four live text files

The four live text files are one model and are all on the release (the encoder is over 100 MB), so the model stays in one place.

## Source and license

**Whisper (transcription).** Both `ggml-*` files are unmodified copies of the files published at [ggerganov/whisper.cpp on Hugging Face](https://huggingface.co/ggerganov/whisper.cpp). They are OpenAI's Whisper `base.en` and `small.en` models converted to ggml format and quantized (q5_1). Whisper's model weights are released by OpenAI under the MIT License.

**Live text while recording.** The `nemo-fastconformer-en-480ms-*` files are NVIDIA's [stt_en_fastconformer_hybrid_large_streaming_multi](https://huggingface.co/nvidia/stt_en_fastconformer_hybrid_large_streaming_multi) (a streaming FastConformer transducer, 480 ms chunks), converted to ONNX and int8-quantized by the sherpa-onnx project. They are unmodified copies of the files at [csukuangfj/sherpa-onnx-nemo-streaming-fast-conformer-transducer-en-480ms-int8](https://huggingface.co/csukuangfj/sherpa-onnx-nemo-streaming-fast-conformer-transducer-en-480ms-int8) @ `df8ed95e`, renamed with the `nemo-fastconformer-en-480ms-` prefix. Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/); the app credits NVIDIA on its licenses screen.
