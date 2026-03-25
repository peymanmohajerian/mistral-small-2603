<!-- DO NOT CHANGE MARKDOWN HEADERS. IF CHANGED, MODEL CARD MAY BE REJECTED BY A REVIEWER -->

<!-- `description.md` is required. -->

Mistral Small 4 is a 119B-parameter Mixture-of-Experts model (6.5B active) that unifies instruction-following, reasoning, and coding capabilities with multimodal input support, 256k context, and native function calling under an Apache 2.0 license.

Mistral Small 4 is a powerful hybrid model that unifies the capabilities of three model families — Instruct, Reasoning (previously Magistral), and Devstral — into a single model. Built on a Mixture-of-Experts architecture with 128 experts and 4 active per token, it delivers 119B total parameters with only 6.5B active parameters, enabling strong performance with efficient inference. The model supports multimodal input (text and images), a 256k token context window, and native function calling with JSON output. Users can switch between a fast instant-reply mode and a reasoning mode with configurable reasoning effort, allowing test-time compute scaling when needed. 

It supports 11+ languages including English, French, German, Spanish, Italian, Portuguese, Dutch, Chinese, Japanese, Polish, and Russian. The vision encoder is trained from scratch to natively support variable image sizes and aspect ratios using RoPE-2D rotary position encoding. Mistral Small 4 is ideal for general chat assistants, coding agents, document parsing and extraction, research assistants, and fine-tuning for specialized tasks.




