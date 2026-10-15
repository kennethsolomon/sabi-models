# sabi-models

Mirror of Whisper Core ML model files used by Sabi, a personal iOS voice journal. Hosted on GitHub Releases because GitHub's CDN is much faster than Hugging Face from the Philippines. The files are byte-identical copies of the upstream files (verified against the Hugging Face SHA-256 / git hashes before upload).

## Releases

| Tag | Model | Files | Size |
|-----|-------|-------|------|
| `whisper-large-v3-turbo-632mb-v1` | `openai_whisper-large-v3-v20240930_turbo_632MB` | 24 | 648,432,373 bytes |

Each file is one release asset. Asset names are the file's path inside the model folder with `/` replaced by `__` (for example `AudioEncoder.mlmodelc__weights__weight.bin`). `manifest.json` lists every file with its `path`, `asset` name, `size` and `sha256`. Clients must check size and SHA-256 of every file after download.

The release also contains `tokenizer.json` and `tokenizer_config.json`, so WhisperKit can load the tokenizer from the model folder without contacting Hugging Face.

## Sources

- Core ML model: [argmaxinc/whisperkit-coreml](https://huggingface.co/argmaxinc/whisperkit-coreml/tree/main/openai_whisper-large-v3-v20240930_turbo_632MB), commit `0f63a7800b00dd0226abd051b906c246e1907482`
- Tokenizer: [openai/whisper-large-v3](https://huggingface.co/openai/whisper-large-v3), commit `06f233fe06e710322aca913c1bc4249a0d71fce1`

## Offline use

Sabi downloads these files once. After that, transcription runs entirely on device and never touches the network: the model and tokenizer are loaded from the local model folder with WhisperKit downloads disabled.

## License

No changes were made to any file. See [NOTICE.md](NOTICE.md).

- WhisperKit Core ML models (argmaxinc/whisperkit-coreml): MIT License, Copyright (c) 2024 Argmax, Inc.
- OpenAI Whisper model weights: MIT License, Copyright (c) 2022 OpenAI ([openai/whisper](https://github.com/openai/whisper/blob/main/LICENSE)).
- Tokenizer files from the openai/whisper-large-v3 Hugging Face repository, which is published under Apache-2.0.
