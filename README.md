# llama-cpp-oai-like-server

### English introduction

A small improvement to `llama.cpp/examples/server/api_like_OAI.py` to support more conversation formats.

`llama.cpp-python` supports setting the chat template by `--chat_format`, but there are always some models whose chat format is not in the supported list.
According to the author's design, you need to modify the code to be compatible with the new format.

In an update in December 2023, llama.cpp/server fixed the Unicode garbled problem.
llama.cpp provides `api_like_OAI.py` to convert the original interface into an OpenAI compatible format. So I added `--chat-format` to it.
You can set more templates in `chat_format.toml`.

For example:
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
