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

## live-test (temporary)

Candidate models for **live text while recording**, used only by a debug-build test in the app to compare speed and accuracy on real phones. Once one is chosen it moves to a versioned folder and this folder and release are deleted.

All three are streaming speech recognizers for [sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx), int8-quantized, copied unmodified from the Hugging Face repos named below (pinned revisions).

| Model | Where | Files (bytes, SHA-256) |
|---|---|---|
| Zipformer, 20M parameters (LibriSpeech). [csukuangfj/sherpa-onnx-streaming-zipformer-en-20M-2023-02-17](https://huggingface.co/csukuangfj/sherpa-onnx-streaming-zipformer-en-20M-2023-02-17) @ `d42f2d9f`. Apache 2.0 | `live-test/zipformer-en-20M/` | `encoder.int8.onnx` 42,845,182 `3810755ce7c3ab26b42a8bcf39d191308fa27fb0f53358823ba46141d03b7eb3`<br>`decoder.int8.onnx` 539,499 `21e2a2acd961b3ac72f55be2f10f1a285e1b0b0ba010d7c0b6eab141411b163c`<br>`joiner.int8.onnx` 259,572 `e085d73b593cf9b0707f370dbd656d58327d3fe36d80d849202ef81df02cb01e`<br>`tokens.txt` 5,048 `49e3c2646595fd907228b3c6787069658f67b17377c60aeb8619c4551b2316fb` |
| Zipformer, chunk 16 / left 128 (LibriSpeech). [csukuangfj/sherpa-onnx-streaming-zipformer-en-2023-06-26](https://huggingface.co/csukuangfj/sherpa-onnx-streaming-zipformer-en-2023-06-26) @ `672fbf1b`. Apache 2.0 | `live-test/zipformer-en-2023-06-26/` | `encoder.int8.onnx` 71,083,163 `563fde436d16cf7607cf408cd6b30909819d03162652ef389c2450ced3f45ac1`<br>`decoder.int8.onnx` 1,307,236 `98da299f471e38bb4e1a8df579b8cc9122d6039576a77e357b3c60f17dd83b02`<br>`joiner.int8.onnx` 259,335 `d944208d660d67c8d72cd2acaeac971fa5ceb8c80e76c1968148846fedd6e297`<br>`tokens.txt` 5,048 `49e3c2646595fd907228b3c6787069658f67b17377c60aeb8619c4551b2316fb` |
| NVIDIA NeMo FastConformer transducer, 480 ms (about 10,000 hours of English). [csukuangfj/sherpa-onnx-nemo-streaming-fast-conformer-transducer-en-480ms-int8](https://huggingface.co/csukuangfj/sherpa-onnx-nemo-streaming-fast-conformer-transducer-en-480ms-int8) @ `df8ed95e`, converted from NVIDIA's `stt_en_fastconformer_hybrid_large_streaming_multi`. CC BY 4.0 | Release `live-test` (the encoder is over 100 MB) | `nemo-fastconformer-en-480ms-encoder.int8.onnx` 131,507,603 `100c5616929a131b5b3c8c8ab0d83aaba2cdcae163acd8d190b4e5ffa5f7d051`<br>`nemo-fastconformer-en-480ms-decoder.int8.onnx` 3,955,864 `4f04431988472f8c7b815f942aa6901976929c9e22353029681fcdb262da0164`<br>`nemo-fastconformer-en-480ms-joiner.int8.onnx` 1,408,182 `d2d8e7290a6a8245a83ed211aa0dd8cdf8effb8a7c64fe392399561111b52f30`<br>`nemo-fastconformer-en-480ms-tokens.txt` 11,896 `618dc110fc2213886b52e063ff42329bbdf37a266ca7705184090fa5f39f3131` |
