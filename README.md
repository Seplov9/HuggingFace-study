# HuggingFace-study

## HuggingFace镜像站：https://hf-mirror.com/

### Linux
`export HF_ENDPOINT=https://hf-mirror.com`

### python
```python
import os
os.environ['HF_ENDPOINT'] = '​hf-mirror.com'
```

## huggingface-cli
网址：https://huggingface.co/docs/huggingface_hub/guides/cli

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
