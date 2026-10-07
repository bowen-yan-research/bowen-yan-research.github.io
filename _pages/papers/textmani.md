---
layout: page
title: "TextMani"
permalink: /papers/textmani/
nav: false
description: "TextMani: Diagnosing and Repairing Constraint Formalization in LLM-Based Robotic Manipulation"
---

**Under review at ICLR 2027**

**Bowen Yan†**, Zhongjie Jia†, Chunyi Li, Bin Zhao, and Guangtao Zhai.

† Equal contribution.

> An LLM-based manipulation pipeline that reasons about physical constraints and uses execution feedback to diagnose and repair their formalization.

## Research question

How can a robot turn a natural-language task into executable physical constraints, and repair the relevant constraints when execution reveals a problem?

## Approach

TextMani connects natural-language task understanding with explicit physical constraint reasoning and action generation. When execution fails, the pipeline uses execution-grounded diagnosis to identify a problem and make a localized repair.

1. Interpret the natural-language task.
2. Reason about physical constraints and generate executable actions.
3. Use execution feedback for failure diagnosis and localized repair.

## Why it matters

The goal is to connect language-based planning with physical execution, so that failures can lead to targeted corrections.

---

[← All publications]({{ '/publications/' | relative_url }}) · [Research overview]({{ '/projects/' | relative_url }})
