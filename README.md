# HuggingFace-study

## Huggingface镜像站：https://hf-mirror.com/

### Linux
`export HF_ENDPOINT=https://hf-mirror.com`

### Windows
`$env:HF_ENDPOINT = "https://hf-mirror.com"`

### python
```python
import os
os.environ['HF_ENDPOINT'] = '​hf-mirror.com'
```

## huggingface-cli
网址：https://huggingface.co/docs/huggingface_hub/guides/cli
安装：`pip install -U "huggingface_hub"`
下载：`hf download Qwen/Qwen3-VL-2B-Instruct`

## 拉取参数
```python
from transformers import GPT2Model, GPT2Tokenizer

model_id = "gpt2"
tokenizer = GPT2Tokenizer.from_pretrained(model_id)
model = GPT2Model.from_pretrained(model_id)

from transformers import AutoTokenizer, AutoModelForCausalLM

tokenizer = AutoTokenizer.from_pretrained("openai-community/gpt2")
model = AutoModelForCausalLM.from_pretrained("openai-community/gpt2")

# 保存到指定目录
tokenizer.save_pretrained("./my-gpt2")
model.save_pretrained("./my-gpt2")

print("GPT-2 全部参数已成功拉取并保存到本地。")
```

当执行 from_pretrained("gpt2") 时，程序的查找逻辑是这样的：

检查本地路径：看看当前目录下有没有叫 gpt2 的文件夹。

检查系统缓存 (Cache)：去 Hugging Face 的默认缓存文件夹（通常在用户目录下的 ~/.cache/huggingface/hub）查找是否已经下载过该模型的 blob 文件。

下载：如果前两步都找不到，才会连接网络从远程仓库拉取。
