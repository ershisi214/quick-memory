# Quick Memory

Turn knowledge points into compact Chinese memory aids: core keywords, a plain-language summary, an accurate memory hook, and a 10-second active-recall question.

把知识点提炼成关键词、一句话总结、记忆钩子和十秒回想题。

## What it does

- Preserves essential terminology, conditions, order, and exceptions.
- Chooses a memory method that fits the material: analogy, action chain, contrast, acronym, causal chain, or hierarchy.
- Favors accuracy over clever but misleading rhymes.
- Keeps the default output short enough for quick review.
- Adds an answer-free recall question by default.

## Install

```bash
npx skills add ershisi214/quick-memory --skill quick-memory -g
```

## Use

Invoke the skill explicitly:

```text
Use $quick-memory to help me remember:
数据库事务具有原子性、一致性、隔离性和持久性。
```

It also applies naturally to requests such as:

```text
提取这段知识的关键词，并用一句口诀帮我快速记住。
```

Default output:

```text
关键词：专业术语（白话锚点）
一句话：说清关键词之间的关系
记忆钩子：准确、简短的口诀或类比
10 秒回想：一道不泄露答案的主动回想题
```

## License

[MIT](LICENSE)
