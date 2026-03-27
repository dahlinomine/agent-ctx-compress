# Agent Context Compressor

![memory](https://img.shields.io/badge/memory-blue?style=flat-square) ![compression](https://img.shields.io/badge/compression-blue?style=flat-square) ![context-window](https://img.shields.io/badge/context--window-blue?style=flat-square)

Lossy and lossless compression algorithms for agent memory to handle 1M+ token histories.

## Overview
Agent Context Compressor is a Python library designed to optimize Long-Context LLM performance by reducing the footprint of massive conversation histories. It utilizes advanced pruning and summarization techniques to pack 1M+ tokens into manageable, high-density context windows without losing critical semantic intent.

## Features
* **Hybrid Compression:** Support for both lossless (redundancy removal) and lossy (semantic summarization) algorithms.
* **Token Budget Management:** Automatically scales compression ratios to fit specific model context limits.
* **Semantic Importance Scoring:** Prioritizes key facts and entities while pruning conversational filler.
* **Seamless Integration:** Designed for agents built with frameworks like LangChain, AutoGPT, or custom loops.

## Installation
Clone the repository and install the necessary dependencies using pip:

```bash
git clone https://github.com/yourusername/agent-ctx-compress.git
cd agent-ctx-compress
pip install -r requirements.txt
```

## Usage
Run the main script to compress a JSON-formatted history file or provide a text string.

```bash
python main.py --input history.txt --ratio 0.5
```

**Example Code:**
```python
from compressor import ContextCompressor

ctx = ContextCompressor(method="semantic")
long_history = "..." # Your 1M token history
compressed_text = ctx.compress(long_history, target_tokens=4000)

print(f"Compressed Context: {compressed_text}")
```

## Contributing
Contributions are welcome! If you have ideas for new compression algorithms or optimizations, please open an issue or submit a pull request. Ensure all code follows PEP 8 standards and includes appropriate test coverage.

## License
This project is licensed under the [MIT License](LICENSE).