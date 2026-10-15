# Neo-Audio-models

Separation models downloaded on demand by the **Neo Audio** browser extension (module 13 "Virtual stage", high-quality mode).
The extension package does not contain them; the first time the mode is enabled it fetches the file from the matching release
here and caches it in IndexedDB.

| Release | File | Size | What |
|---|---|---|---|
| `models-v1` | `htdemucs-dyn-fp32.onnx` | 168.4 MB | htdemucs (Demucs v4, hybrid transformer) core network, fp32, dynamic segment length 0.5–5 s; STFT / iSTFT are done outside the graph by the extension |

Export: `tools/nn/export_htdemucs.py --dynamic` in the Neo Audio repository (torch 2.8, opset 17; attention and the time-branch
view rewritten to keep the sequence length dynamic).

## License

The weights are derived from Meta's `htdemucs` checkpoint, released under the MIT License
(https://github.com/facebookresearch/demucs). This repository redistributes them under the same license — see `LICENSE`.
