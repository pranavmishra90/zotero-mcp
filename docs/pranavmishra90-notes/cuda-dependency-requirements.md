# CUDA Dependency Requirements

The default installation method via `uv` will automatically pull the CUDA-accelerated version of PyTorch, even if a CUDA-capable GPU is not present on your system. 

This behavior was noted on a Windows 11 WSL ubuntu24.04 machine, on a computer that does not have an NVIDIA GPU.

## Dependencies

Exploring the dependency tree, we find that `torch` is a dependency of `sentence-transformers`, which is itself a dependency of `zotero-mcp`.

```bash

----- PACKAGES NEEDING 'sentence-transformers' -----

Resolved 199 packages in 13ms
sentence-transformers v5.2.0
└── zotero-mcp


----- 'sentence-transformers' DEPENDENCIES -----

Resolved 199 packages in 5ms
sentence-transformers v5.2.0
├── huggingface-hub v0.36.0
│   ├── filelock v3.20.1
│   ├── fsspec v2025.12.0
│   ├── hf-xet v1.2.0
│   ├── packaging v25.0
│   ├── pyyaml v6.0.3
│   ├── requests v2.32.5
│   │   ├── certifi v2025.11.12
│   │   ├── charset-normalizer v3.4.4
│   │   ├── idna v3.11
│   │   └── urllib3 v2.3.0
│   ├── tqdm v4.67.1
│   └── typing-extensions v4.15.0
├── scikit-learn v1.8.0
│   ├── joblib v1.5.3
│   ├── numpy v2.4.0
│   ├── scipy v1.16.3
│   │   └── numpy v2.4.0
│   └── threadpoolctl v3.6.0
├── scipy v1.16.3 (*)
├── torch v2.9.1
│   ├── filelock v3.20.1
│   ├── fsspec v2025.12.0
│   ├── jinja2 v3.1.6
│   │   └── markupsafe v3.0.3
│   ├── networkx v3.6.1
│   ├── nvidia-cublas-cu12 v12.8.4.1
│   ├── nvidia-cuda-cupti-cu12 v12.8.90
│   ├── nvidia-cuda-nvrtc-cu12 v12.8.93
│   ├── nvidia-cuda-runtime-cu12 v12.8.90
│   ├── nvidia-cudnn-cu12 v9.10.2.21
│   │   └── nvidia-cublas-cu12 v12.8.4.1
│   ├── nvidia-cufft-cu12 v11.3.3.83
│   │   └── nvidia-nvjitlink-cu12 v12.8.93
│   ├── nvidia-cufile-cu12 v1.13.1.3
│   ├── nvidia-curand-cu12 v10.3.9.90
│   ├── nvidia-cusolver-cu12 v11.7.3.90
│   │   ├── nvidia-cublas-cu12 v12.8.4.1
│   │   ├── nvidia-cusparse-cu12 v12.5.8.93
│   │   │   └── nvidia-nvjitlink-cu12 v12.8.93
│   │   └── nvidia-nvjitlink-cu12 v12.8.93
│   ├── nvidia-cusparse-cu12 v12.5.8.93 (*)
│   ├── nvidia-cusparselt-cu12 v0.7.1
│   ├── nvidia-nccl-cu12 v2.27.5
│   ├── nvidia-nvjitlink-cu12 v12.8.93
│   ├── nvidia-nvshmem-cu12 v3.3.20
│   ├── nvidia-nvtx-cu12 v12.8.90
│   ├── setuptools v80.9.0
│   ├── sympy v1.14.0
│   │   └── mpmath v1.3.0
│   ├── triton v3.5.1
│   └── typing-extensions v4.15.0
├── tqdm v4.67.1
├── transformers v4.57.3
│   ├── filelock v3.20.1
│   ├── huggingface-hub v0.36.0 (*)
│   ├── numpy v2.4.0
│   ├── packaging v25.0
│   ├── pyyaml v6.0.3
│   ├── regex v2025.11.3
│   ├── requests v2.32.5 (*)
│   ├── safetensors v0.7.0
│   ├── tokenizers v0.22.1
│   │   └── huggingface-hub v0.36.0 (*)
│   └── tqdm v4.67.1
└── typing-extensions v4.15.0
(*) Package tree already displayed

```