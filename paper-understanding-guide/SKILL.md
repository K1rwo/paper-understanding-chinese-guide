---
name: paper-understanding-guide
description: Reply directly in Codex chat with a detailed Simplified Chinese understanding guide for a single academic paper from a PDF, abstract, full text, screenshots, or references. Use when the user wants an accessible guide for someone who has not read the paper, with plain-language explanations, concrete examples, input-output tables, method walkthroughs, evidence, limitations, and a clear explanation of what the paper's method can and cannot do. Do not create a separate document or file unless the user explicitly asks for one.
---

# Paper Understanding Guide

## Purpose

Reply directly in the Codex conversation with a clear, structured Simplified Chinese guide that feels like a readable explainer rather than a generic paper summary.

The target reader has not read the paper. After reading the guide, they should understand:

- what problem the paper tries to solve
- what the proposed system, model, theory, or method can do
- what inputs and outputs it uses
- what method makes it work
- what evidence supports it
- what it cannot do
- how to reuse the paper for learning or writing

The final answer must be in Simplified Chinese. Keep English technical terms only when they are standard or useful.

All section headings, table headers, capability labels, and explanatory prose in the final answer must be Simplified Chinese. The English headings in this SKILL.md are internal meaning labels only. Do not copy them into the final answer.

Do not create a .md, .docx, .pdf, canvas, or any other file unless the user explicitly asks for a saved artifact. The default deliverable is a normal Codex chat reply.

## Target Style

Match the style of an accessible paper guide:

- Use direct Simplified Chinese guide headings. The headings should mean:
  - What is this paper really trying to do?
  - What object does it process or study?
  - What exactly can it do?
  - What are its inputs and outputs?
  - How does it make these things work?
  - What can it not do?
  - The simplest way to understand it
- Explain from the reader's point of view, not in the abstract's order.
- Prefer short paragraphs plus concrete examples.
- Use Simplified Chinese capability labels meaning: input, output, concrete example, and use case.
- Use simple fenced text blocks for examples when that makes input-output relations clearer.
- Use tables for task mapping, evidence summary, and final synthesis.
- Be honest about what the paper does not prove.
- Avoid sounding like a formal review form unless the user explicitly asks for a review.

## Inputs

Accept any of these:

- PDF or local file path
- title, DOI, arXiv ID, URL, abstract, screenshots, full text, or references
- the user's own research purpose or questions

If a PDF or URL is provided, extract or verify bibliographic metadata before analysis: title, authors, year, DOI/arXiv/link, publication status if available, and provided material type.

For current or unstable metadata, verify using authoritative sources such as arXiv, DOI landing pages, publisher pages, or official project pages. Mark unverified items explicitly.

## Workflow

1. Identify the paper and material type.
2. Extract the paper's problem, task setting, inputs, outputs, method, experiments, results, and limitations.
3. Separate evidence from inference. If the paper does not explicitly state a research question or limitation, label the statement as inferred.
4. Reorganize the explanation around reader questions: what is it, what can it do, how does it work, what proves it works, what can it not do.
5. Explain the paper for a reader who has not read it. Prefer concrete examples over generic summary.
6. Include page, section, figure, or table locations for quoted or reusable claims whenever possible.
7. End with a compact "simplest understanding" summary and a final synthesis table.

## Required Output Structure

Use this structure unless the user asks for a different format. Render the section titles in natural Simplified Chinese, not in English.

### Title

Use:

`# <paper or method name> paper understanding guide`

Translate this title pattern into natural Simplified Chinese in the final answer.

Then give brief metadata:

- paper
- core object
- core goal
- one-sentence summary

Translate these metadata labels into Simplified Chinese in the final answer.

### 1. What Is This Paper Really Trying To Do?

Render this heading in Simplified Chinese in the final answer.

Explain the field background, the practical or theoretical problem, what previous work already did, what gap remains, and why the paper matters.

For technical system papers, explicitly state the fragmentation, bottleneck, or missing capability the system tries to solve.

### 2. What Object Does It Process Or Study?

Render this heading in Simplified Chinese in the final answer.

Clarify the core object being modeled or analyzed.

Examples:

- 3D skeleton motion sequence, not raw video
- probability distribution, not a deterministic label
- citation graph, not the full paper text
- clinical outcome, not patient satisfaction

Make common misunderstandings explicit.

### 3. What Exactly Can It Do?

Render this heading in Simplified Chinese in the final answer.

List the proposed system/model/method's capabilities in concrete terms.

For each capability, include:

- input
- output
- what the capability means
- a specific example
- possible use case

Recommended capability block. Translate labels into Simplified Chinese in the final answer:

```text
Input:
...

Output:
...

Concrete example:
...

Use case:
...
```

### 4. What Are Its Inputs And Outputs?

Render this heading in Simplified Chinese in the final answer.

Make the input-output mapping explicit. If the paper has multiple tasks, create a task table:

| Task | Input | Output | Example |
|---|---|---|---|

Translate all table headers into Simplified Chinese in the final answer.

Clarify what the system does not output, especially when users may confuse representations such as text, video, mesh, skeleton, labels, embeddings, or probabilities.

### 5. How Does It Make These Things Work?

Render this heading in Simplified Chinese in the final answer.

Explain the core method in plain language while preserving key terms.

Cover:

- overall architecture or research design
- key modules or variables
- data flow
- training or analysis process
- objective functions or statistical methods when central
- why the method fits the research question

For technical papers, first give a simple flow:

```text
raw input
    ->
module A
    ->
intermediate representation
    ->
module B
    ->
final output
```

Translate node labels in this flow into Simplified Chinese in the final answer.

Then explain each key module in its own subsection.

### 6. Why Is It More Unified Or More Effective Than Prior Methods?

Render this heading in Simplified Chinese in the final answer.

If the paper compares with prior work, explain the difference in plain language.

Use before/after or old/new framing when useful:

```text
Before:
Model A does task 1; model B does task 2; model C does task 3.

This paper:
One unified framework handles multiple related tasks.
```

Translate this before/after framing into Simplified Chinese in the final answer.

### 7. What Did The Experiments Prove?

Render this heading in Simplified Chinese in the final answer.

Summarize experiments, datasets, samples, benchmarks, metrics, tables, figures, and main numerical results.

For each major result:

- say what was tested
- report the key number or qualitative evidence
- explain what the metric means
- state whether it supports the paper's claim
- distinguish main results from supplementary results

### 8. What Do Ablations Or Mechanism Analyses Show?

Render this heading in Simplified Chinese in the final answer.

When the paper has ablations, explain what each ablation proves:

- what was removed or changed
- what happened to performance
- what conclusion is justified

If there are no ablations, say so and explain how that affects credibility.

### 9. How Do The Authors Interpret The Results?

Render this heading in Simplified Chinese in the final answer.

Explain the authors' interpretation, proposed mechanisms, consistency or conflict with prior work, and which explanations are strong or weak.

### 10. Contributions

Render this heading in Simplified Chinese in the final answer.

Assess:

- theoretical contribution
- methodological contribution
- empirical contribution
- practical or application value

If a contribution is weak or absent, say so directly.

### 11. What Can It Not Do?

Render this heading in Simplified Chinese in the final answer.

Include both author-stated limitations and your own critical assessment.

Consider:

- data or sample limits
- method limits
- causal inference limits
- external validity and generalization
- measurement limits
- computation or deployment constraints
- possible bias
- tasks the system cannot perform

Be concrete. Do not let the reader leave with an exaggerated understanding of the paper.

For system/model papers, explicitly list non-capabilities when relevant:

- not a video generator
- not a full simulation engine
- not a causal proof
- not validated on all real-world settings
- not lightweight if it depends on a large model

Adapt these to the paper. Do not include irrelevant non-capabilities.

### 12. Credibility Assessment

Render this heading in Simplified Chinese in the final answer.

Evaluate evidence strength:

- whether the method supports the conclusion
- whether results are sufficient
- whether claims are overextended
- missing variables or alternative explanations
- confidence level: strong trust, medium trust, or cautious trust

Explain the rating briefly.

### 13. Relationship To The User's Research Or Learning

Render this heading in Simplified Chinese in the final answer.

Explain how the paper can be used for:

- literature review
- research background
- method borrowing
- research question design
- future research directions
- reading notes or thesis writing

### 14. Citable Points

Render this heading in Simplified Chinese in the final answer.

Provide 5-10 reusable points. Each point must include:

- Chinese summary
- original evidence location, such as section, page, figure, table, or paragraph
- suitable writing location: introduction, literature review, methods, discussion, etc.

Do not fabricate quotations or references.

### 15. Glossary

Render this heading in Simplified Chinese in the final answer.

List key terms from the paper and explain them in Simplified Chinese. Keep the English term when useful.

### 16. The Simplest Way To Understand It

Render this heading in Simplified Chinese in the final answer.

End the narrative with a compact "if you remember only one thing" summary.

Use this format. Translate labels into Simplified Chinese in the final answer:

```text
It can do:
...

It works by:
...

It outputs:
...

It does not output:
...
```

Then provide a one-sentence final summary.

### 17. Final Synthesis Table

Render this heading in Simplified Chinese in the final answer.

End with this table:

| Module | Paper Content | My Understanding | Writing Value |
|---|---|---|---|

Translate all table headers into Simplified Chinese in the final answer.

## Style Requirements

- Write in clear Simplified Chinese.
- Be detailed but organized.
- Avoid vague praise such as "the paper is important" without explaining why.
- Use concrete examples, especially for "what it can do" and "input/output".
- Prefer explanatory tables for complex task mappings.
- State uncertainty explicitly.
- Do not overclaim beyond the paper's evidence.
- If the paper is technical, translate the method into an intuitive workflow before discussing equations or metrics.
- Preserve a guide-like voice with natural Simplified Chinese phrases equivalent to: "you can understand it as...", "more directly...", and "concrete example...".
- Avoid long uninterrupted paragraphs. Use section headings, tables, and example blocks to keep it readable.

## Quality Check

Before finalizing, verify that the guide answers these questions:

- Can someone who has not read the paper explain what problem it solves?
- Can they state the model/method's inputs and outputs?
- Can they give at least three concrete examples of what it can do, if applicable?
- Can they explain the key method in a simple flow?
- Can they distinguish what the paper proves from what it merely suggests?
- Can they state what the method cannot do?
- Does the output feel like a practical guide rather than a generic academic summary?
