# llama-cpp-oai-like-server

### Introduction

This repository introduces a minor enhancement to `llama.cpp/examples/server/api_like_OAI.py` aimed at expanding support for various chat formats.

`llama.cpp-python` allows the customization of the chat template through the `--chat_format` option. However, certain models may not have their chat formats included in the provided list of supported formats. In accordance with the author's design, code modifications are necessary to ensure compatibility with new formats.

In a December 2023 update, llama.cpp/server resolved the Unicode garbled problem. The repository includes `api_like_OAI.py`, which serves to convert the original interface into a format compatible with OpenAI. As part of this adaptation, I introduced the `--chat-format` option. Users can define additional templates in the `chat_format.toml` file.

Here's an example of usage:

```bash
./server -m minichat-3b.q8_0.gguf
python api_like_OAI.py --chat-format minichat-uncensored
```
Yes, you can use prompt injection to jailbreak. For specific examples, please refer to `chat_format.toml`

---

### 中文介绍

对`llama.cpp/examples/server/api_like_OAI.py`的一点小改进，使其能够支持更多的对话格式。

`llama.cpp-python`支持通过`--chat_format`设置对话模板，但总有一些模型的对话格式不在支持列表中。
根据作者的设计，新增模板需要修改代码才能支持，这让模板支持变得复杂。

在2023年12月的一次更新中，llama.cpp/server修复了Unicode的乱码问题。
llama.cpp提供了api_like_OAI.py用以将原始接口转换为OpenAI兼容的格式，我为其新增了`--chat-format`。
你可以在`chat_format.toml`中设置更多模板。

例如：
```bash
./server -m minichat-3b.q8_0.gguf
python api_like_OAI.py --chat-format minichat-uncensored
```

你甚至可以使用提示词注入来绕过模型审查，具体方法请参考`chat_format.toml`
