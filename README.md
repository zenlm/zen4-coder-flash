---
license: mit
language:
- en
- zh
tags:
- zen
- zen-lm
- zenlm
- code
- moe
- abliterated
pipeline_tag: text-generation
library_name: transformers
---

# Zen Coder Flash 31B

Code-focused MoE model from the [Zen LM](https://zenlm.org) family by Hanzo AI.

**Architecture**: Zen MoDE (Mixture of Distilled Experts)
**Parameters**: 31B total / 3B active (MoE)
**Context**: 131,072 tokens
**License**: MIT

## Abliteration

Zen Coder Flash 31B weights are derived from an abliterated base model. Abliteration removes
refusal behavior by identifying and nullifying the "refusal direction" in the model's
residual stream.

**Method**: Directional ablation on the residual stream across all layers
**Implementation**: [hanzoai/remove-refusals](https://github.com/hanzoai/remove-refusals) — Hanzo's production abliteration toolkit
**Technique**: [Refusal in LLMs is mediated by a single direction](https://www.lesswrong.com/posts/jGuXSZgv6qfdhMCuJ/refusal-in-llms-is-mediated-by-a-single-direction) — Arditi et al.
**Effect**: Removes refusal behaviors while preserving all other capabilities
**Identity layer**: Zen identity added via system prompt — full LoRA fine-tuning planned

Abliteration is a feature, not a limitation. It enables unrestricted research,
security testing, and applications where safety guardrails are managed at the
application layer rather than baked into model weights.

## Links

- **Website**: https://zenlm.org
- **GitHub**: https://github.com/zenlm
- **HuggingFace**: https://huggingface.co/zenlm
