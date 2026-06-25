# Paper Understanding Guide

`paper-understanding-guide` is a Codex skill for turning a single academic paper into a clear Simplified Chinese understanding guide.

It is designed for readers who have not read the paper yet. The skill explains what the paper is trying to do, what the proposed method can and cannot do, what its inputs and outputs are, how the method works, what evidence supports it, and how the paper can be reused for study or writing.

## What It Does

- Produces the answer directly in the Codex chat.
- Uses Simplified Chinese by default.
- Explains papers in a guide-like style, not as a generic abstract summary.
- Emphasizes concrete examples, input-output mappings, method walkthroughs, evidence, limitations, credibility, and writing value.
- Does not create separate files unless the user explicitly asks for a saved artifact.

## Repository Structure

```text
paper-understanding-guide/
  SKILL.md
  agents/
    openai.yaml
```

## Installation

Copy the skill folder into your Codex skills directory:

```text
~/.codex/skills/paper-understanding-guide/
```

On Windows, this is usually:

```text
C:\Users\<you>\.codex\skills\paper-understanding-guide\
```

Then restart Codex or reload skills if needed.

## Example Prompt

```text
请使用 paper-understanding-guide，直接在 Codex 对话里用简体中文生成这篇论文的理解 Guide，不要创建单独文件。
```

You can provide a PDF, arXiv link, DOI, abstract, full text, screenshots, or references.

## Output Style

The generated guide is organized around practical reader questions, such as:

- 这篇论文到底想干什么？
- 它处理的对象是什么？
- 它到底能做什么？
- 它的输入和输出到底是什么？
- 它是怎么做到这些事情的？
- 它在实验中证明了什么？
- 它不能做什么？
- 最简单的理解方式

The final result should help a reader explain the paper without having read the original text first.
