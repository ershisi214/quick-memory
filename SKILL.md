---
name: quick-memory-hook
description: Turn user-provided knowledge points into concise Chinese memory aids by extracting core keywords, stating the relationship in one plain-language sentence, creating an accurate mnemonic or analogy, and adding a quick active-recall check. Use when the user asks to quickly remember, summarize, distill, recite, memorize, make a口诀/助记句/记忆钩子, extract keywords from study material, or convert a concept into a short review aid.
---

# Quick Memory Hook

Turn one knowledge unit into the smallest accurate package that the user can understand and recall quickly.

## Core Workflow

1. Understand the source before compressing it. Identify what the knowledge point means, not only which words occur most often.
2. Split mixed material into minimal independent units. Keep one definition, rule, comparison, process, or causal chain per unit.
3. Extract 3-5 indispensable keywords. Preserve required technical terms, conditions, order, negation, and exceptions. Pair unfamiliar terms with short plain-language anchors, such as `原子性（全做或全不做）`.
4. Express the relationship among the keywords in one plain Chinese sentence. Prefer cause, contrast, sequence, or structure over a loose list.
5. Select the memory device that matches the knowledge structure.
6. Check that the memory device can reconstruct the original meaning without introducing a false rule.
7. Add one answer-free recall prompt that can be attempted in about 10 seconds. Include it by default because retrieval strengthens memory; omit it only when the user explicitly asks for no question.

Do not invent missing facts. If the source is ambiguous or internally inconsistent, identify the uncertainty before creating a mnemonic.

## Select a Memory Device

- **Definition or abstract principle**: use a concrete everyday analogy, preferably from a context familiar to the learner, then preserve the boundary where the analogy stops applying.
- **Ordered process**: use an action chain or short story whose order matches the real steps.
- **Parallel list**: use initials, rhythm, chunking, or one vivid scene that covers every item.
- **Cause and effect**: use an arrow-like verbal chain: cause -> mechanism -> result.
- **Comparison or easily confused concepts**: use a symmetric contrast sentence that highlights the single decisive difference.
- **Formula or rule**: translate the formula into a verbal relationship; retain variables and conditions.
- **Classification or hierarchy**: use an umbrella, tree, or container relationship instead of flattening levels.

Prefer semantic hooks over decorative rhymes. Never sacrifice correctness merely to rhyme, shorten, or sound clever.

## Default Output

Keep the response compact and use this format:

```text
关键词：术语1（白话锚点）、术语2（白话锚点）、术语3（白话锚点）
一句话：用一句大白话说清这些词之间的关系。
记忆钩子：不超过约 20 个汉字；必要时可稍长以保证准确。
10 秒回想：一个不泄露答案的问题。
```

For multiple independent units, repeat the four-line block under short numbered headings. Do not create a long study guide unless requested.

## Quality Gate

Before responding, verify all of the following:

- The learner can understand the sentence without already memorizing the source.
- Required technical terms remain visible alongside their plain-language anchors.
- Each keyword is necessary; no important condition or exception disappeared.
- The hook maps back to every keyword in the correct relationship or order.
- The analogy does not imply a fact that the source does not support.
- The recall prompt tests retrieval rather than recognition and does not contain the answer.
- The complete default answer stays short enough to scan once.

If the source is too dense to satisfy these checks, split it rather than over-compressing it.

## Optional Enhancements

Offer at most one relevant enhancement after the default output when it would materially improve retention. Ask briefly instead of adding it automatically:

- A cloze or two-sided flashcard for facts that need repeated recall.
- A contrast card for commonly confused concepts.
- A tiny flow or hierarchy diagram for sequences and layered structures.
- A concrete example and counterexample when the concept boundary is unclear.
- A second mnemonic style when the first hook may not suit the learner.

Do not offer an enhancement when the four-line answer is already sufficient. Keep the 10-second recall prompt by default. Honor explicit requests such as "只要一句话", "不要题目", or "展开解释" by adjusting the format.

## Example

Input:

```text
数据库事务具有原子性、一致性、隔离性和持久性。
```

Output:

```text
关键词：原子性（全做或全不做）、一致性（状态正确）、隔离性（互不干扰）、持久性（结果不丢）
一句话：事务要么完整成功要么全部撤销，执行时彼此隔离，前后状态正确且提交结果永久保存。
记忆钩子：原子全做，一致做对，隔离不扰，持久不丢。
10 秒回想：事务可靠性的四个保证分别解决什么问题？
```
