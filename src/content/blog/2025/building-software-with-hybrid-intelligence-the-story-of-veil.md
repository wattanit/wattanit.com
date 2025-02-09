---
title: "Building Software with Hybrid Intelligence: The Story of Veil"
pubDatetime: 2025-02-09T18:40:00+07:00
tags:
  - artificial intelligence
  - software development
description: A journey of building Veil, a command-line encryption tool, using hybrid intelligence - where human expertise and AI capabilities work as equal partners. Learn how this approach turned weeks of development work into a 12-hour project, and what it means for the future of software development.
---

# Building Software with Hybrid Intelligence: The Story of Veil

Software development has changed dramatically with the rise of AI assistance, yet some fundamental challenges remain unchanged - particularly the challenge of creating sustainable software. The solution might lie in _hybrid intelligence_: a new paradigm where human expertise and AI capabilities work together as equal partners, each handling the aspects they do best. This goes beyond simple AI assistance - it's a complete rethinking of how software is developed. This post shares my experience creating Veil, a command-line encryption tool, using this hybrid approach that turned what could have been weeks of work into a 12-hour project.

## Part 1: Why Create Another Encryption Tool?

### The Problem

Looking for a reliable encryption tool, I found myself facing a common situation: choose between proprietary software that might disappear when the company does, or open-source alternatives that haven't seen meaningful updates in years. Neither option felt future-proof.

The solution? Create my own. The reasoning was simple: if I'm going to rely on software that might not last, I might as well make one that I can rebuild myself when needed.

### Veil's Approach

Veil isn't trying to revolutionize encryption. Instead, it aims to be straightforward and adaptable across different use cases, even if that means making some compromises in advanced security features. The focus is on being transparent and maintainable rather than having the most sophisticated features.

### Technical Overview

Veil works as a command-line interface (CLI) tool that handles file encryption and decryption. Its design prioritizes clarity and ease of use - you provide an input file, and it handles the encryption or decryption based on straightforward commands. While this might sound basic, the underlying implementation deals with complex low-level programming to ensure reliable encryption operations.

## Part 2: Development Through Hybrid Intelligence

### A Different Way to Build Software

Traditional software development typically follows a pattern: programmers design the structure, plan the implementation, and write code line by line. Even with modern AI coding assistants like GitHub Copilot, developers still need to think through each step of the implementation, using AI mainly to help with syntax and boilerplate code.

Hybrid intelligence takes a different approach. Instead of focusing on how to write the code, the emphasis shifts to what we want the software to do. This might sound subtle, but it fundamentally changes the development process.

### The Two-Phase Development Process

#### Phase 1: Requirements making

The first phase involves no coding at all. Instead, it's a collaborative brainstorming process between human expertise and multiple AI agents. The goal is to create a clear, detailed specification of the desired outcome. Unlike traditional requirements that often focus on implementation details, these requirements focus heavily on describing the end result we want to achieve.

This phase resulted in a concise but comprehensive document that laid out exactly what Veil needed to do, without getting bogged down in how to do it. The document became our source of truth, something both human and AI could refer to throughout the development process.

#### Phase 2: Implementation

With clear requirements in hand, the actual coding phase began. Here, AI took the lead in writing code while human oversight ensured everything aligned with the requirements. This is where an interesting challenge emerged: AI tends to follow common programming practices, which sometimes conflicted with our specific requirements.

For example, several bugs occurred when the AI automatically followed common encryption implementation patterns instead of our specified approach. The human role became crucial in spotting these discrepancies - places where the code followed general best practices rather than our specific requirements.

### Real-World Example: Debugging with Hybrid Intelligence

One particular challenge highlighted the strength of this approach. During development, we encountered bugs where the AI had implemented parts of the encryption logic following common industry practices rather than our specified requirements. While these practices were generally good, they didn't align with our goal of simplicity and maintainability.

A human developer working alone might have spent hours tracking down these inconsistencies. With hybrid intelligence, the process was different. The human's role was to spot patterns of inconsistency - places where the code didn't match our requirements document - while the AI could quickly propose and implement fixes once the discrepancy was identified.

### Time and Effort Breakdown

The numbers tell an interesting story:

- Initial requirements and design: 2-3 hours
- Core development: 5-6 hours
- Bug fixing and verification: ~4 hours
- Total time: 12 hours
- Traditional development estimate: 1-2 weeks

What's notable isn't just the time saved, but how the time was spent. Instead of writing code, the human effort focused on two key activities: clearly defining what we wanted the software to do, and verifying that the implementation matched those requirements. This is a fundamental shift from traditional development, where programmers spend most of their time figuring out how to implement features.

## Conclusion: The Future of Software Development

Building Veil taught me something important about software development in the age of AI. **The key to effective hybrid intelligence isn't just having access to AI tools - it's changing how we think about development entirely.** Our role is evolving from writing code to becoming specialists in defining clear requirements and ensuring quality outcomes.

This shift might be exactly what we need to create more sustainable software. When we focus on clearly describing what we want rather than how to build it, we create software that's easier to understand, maintain, and if necessary, rebuild.

Veil is available on GitHub (https://github.com/wattanit/veil), not just as an encryption tool, but as an example of what's possible with hybrid intelligence development. Whether you're interested in the tool itself or the development approach behind it, I encourage you to take a look and consider how this might change your own development practices.
