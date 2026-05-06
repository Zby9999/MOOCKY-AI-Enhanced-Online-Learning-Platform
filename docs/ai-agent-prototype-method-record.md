# AI-Agent-Assisted Prototyping Method Record

## Working Title

From Hi-Fi Figma Screens to a Functional Demo Website: A Design-System-Guided AI Agent Workflow for Rapid Online Learning Platform Prototyping

## Document Purpose

This document records the experimental process behind MOOCKY: moving from several high-fidelity Figma screens into a usable demo website through a workflow that combines design evidence, Markdown-based agent instructions, a seed design system, and iterative AI-assisted implementation.

The intended reader is a professor or research mentor who may be interested in:

- practical AI-assisted design-to-code workflows
- human-AI collaboration in interface prototyping
- design-system governance for AI agents
- rapid prototyping methods for educational technology products
- possible research or implementation opportunities based on the MOOCKY case

## Target Reader

The target reader is Professor Can Liu at the School of Creative Media, City University of Hong Kong.

Public profile basis:

- CityUHK SCM profile: https://www.scm.cityu.edu.hk/people/liu-can
- Personal research page: https://sweb.cityu.edu.hk/canliu/publication.html
- SCM research overview: https://www.scm.cityu.edu.hk/en/research

Based on these public sources, the document should be positioned closer to an HCI research memo than a product portfolio. The strongest fit is not "AI generated a website", but "a human-led, document-constrained AI workflow for future interface prototyping".

## Reader-Fit Document Characteristics

The professor-facing version should have the following characteristics:

- HCI framing first: describe the work as a prototyping and interaction-design workflow, not as a purely frontend engineering project.
- Empirical orientation: connect the process to user needs, design evidence, verification loops, and future evaluation plans.
- Future interface angle: frame MOOCKY as a case for AI-mediated learning interfaces and agent-assisted design-to-code workflows.
- Human-AI collaboration clarity: explain what the human designer controlled and what the AI agent executed.
- Method traceability: show how Figma evidence, Markdown guide files, tokens, and browser verification formed a repeatable workflow.
- Concrete artifact evidence: include direct links to the GitHub Markdown file, the demo website, key guide files, and screenshots when available.
- Research potential: end with open research questions about design-system governance, AI agents, and accountable design-to-code translation.
- Careful claims: avoid saying the method is fully validated. Present it as a case-based, early-stage, experimental workflow with promising research directions.
- Compatibility with SCM: connect the work to creative media, HCI, AI-assisted input, collaborative interaction, and practical prototyping.
- Concise professor reading path: make the first page skimmable, with abstract, contribution, method diagram/list, artifact links, and next-step questions.

## Final Submission Requirements

- Final document language: English.
- Primary source file: `docs/ai-agent-prototype-method-record.md`.
- Direct GitHub Markdown link to include in the document: https://github.com/Zby9999/MOOCKY-AI-Enhanced-Online-Learning-Platform/blob/main/docs/ai-agent-prototype-method-record.md
- Final export format: DOCX.
- Planned DOCX output path in this workspace: `output/doc/ai-agent-prototype-method-record.docx`.
- The DOCX should preserve academic memo readability: title, abstract, section headings, artifact links, concise paragraphs, and an appendix-like evidence checklist if needed.

## Core Claim

The MOOCKY prototype process suggests that AI agents can become more useful for complex interface prototyping when they are not used as unconstrained code generators, but are instead guided by a layered set of design and execution documents.

In this workflow, Markdown files act as an operational bridge between design intent and implementation behavior. They define what the agent should treat as evidence, how visual rules should be prioritized, how uncertainty should be documented, and when a one-off page decision should be promoted into reusable design-system knowledge.

## One-Sentence Summary

MOOCKY used a document-guided AI agent workflow to transform a small set of Hi-Fi Figma references into a coherent, interactive demo website while preserving design-system consistency, implementation traceability, and room for future research.

## Background

MOOCKY is an AI-scaffolded online learning platform prototype. The product concept focuses on bringing familiar AI interactions into online courses so learners can receive timely, course-aware support without being forced into distracting or uncomfortable social interactions.

The prototype began with high-fidelity Figma design references and gradually developed into a working demo website. During this process, the work expanded beyond simple screen replication. It required:

- extracting reusable design rules from Hi-Fi references
- distinguishing authoritative Figma evidence from exploratory frames
- building a shared design-system language called Lumen Atlas
- translating visual rules into tokens, components, layout rules, interaction rules, and agent instructions
- using AI agents to implement, verify, revise, document, and deploy prototype surfaces

## Why This Is Worth Documenting

This process is experimental because it treats AI-assisted prototyping as a governed design process rather than a shortcut from prompt to code. The key contribution is not only that an AI agent helped generate implementation code. The more important contribution is that the agent was constrained by a living documentation system.

The workflow shows a possible model for design-to-code collaboration where:

- Figma provides visual and structural evidence.
- Markdown documents define design authority and execution rules.
- Tokens and component notes translate visual intent into implementation contracts.
- AI agents perform implementation, verification, and documentation while following explicit constraints.
- The human designer remains responsible for evidence selection, design judgment, prioritization, and final decisions.

## Method Overview

### 1. Evidence Selection From Figma

The project did not treat every Figma frame as equally authoritative. Approved Figma nodes were listed explicitly, and each node had a defined evidence boundary. For example, a Button component frame could be used to infer button purposes, states, and hover behavior, but not unrelated typography or page layout rules.

This reduced the risk of the AI agent over-generalizing from attractive but experimental visual references.

### 2. Design-System Translation

Design decisions were translated into a seed design system called Lumen Atlas. The system used a hierarchy of source documents:

- `docs/design-system.md` as the normative design source
- `docs/component-specs.md` as the implementation companion
- `tokens.json` as the machine-readable implementation contract
- `design-system/*` files as the evolving seed layer
- `AGENTS.md` as the execution guide for AI agents

This allowed page-level implementation work to feed back into reusable design-system knowledge when appropriate.

### 3. Markdown-Guided Agent Execution

Multiple Markdown files were used as operational constraints for the AI agent. These documents defined:

- evidence priority
- Figma evidence whitelist
- typography, radius, icon, padding, shadow, blur, gradient, and button rules
- prototype acceptance requirements
- deployment rules
- documentation update rules
- page-specific portfolio and research writing rules

The agent was therefore not asked to simply "make it look good." Instead, it was asked to work inside a structured design and documentation environment.

### 4. Iterative Implementation And Verification

The prototype was implemented as a working website, with local builds, browser checks, and deployment verification used to close the loop. UI updates were expected to be verified through Playwright screenshots where possible, including responsive widths and theme checks when relevant.

This step connected design quality with running software behavior.

### 5. Reflection And Documentation

The process produced not only code, but also documentation artifacts. These artifacts recorded implementation lessons, AI system prompts, design-system decisions, component boundaries, and project memory. This made the prototype process more traceable and easier to continue across sessions.

## Preliminary Contribution

The main contribution of this case is a practical workflow for agentic prototyping:

> A human-led, evidence-constrained, documentation-driven AI agent workflow can help transform Hi-Fi interface references into an interactive demo website while preserving design-system consistency and design rationale.

Possible academic framings include:

- human-AI co-creation for interaction design
- design-system governance for generative AI tools
- prompt engineering as operational design documentation
- AI-assisted design-to-code translation
- rapid prototyping methods in educational technology
- traceability and accountability in AI-generated interface implementation

## Evidence To Collect

The following evidence should be gathered or refined before sending this document to a professor:

- before/after screenshots: original Hi-Fi Figma references and final website pages
- timeline of prototype evolution
- list of key Markdown guide files and their roles
- examples of design rules that prevented inconsistent AI output
- examples of Figma evidence boundaries
- examples of code or UI changes produced through the agent workflow
- deployment URL and short demo path
- reflection on what worked, what failed, and what remains manual
- potential research questions derived from the process

## Potential Research Questions

- How can design-system documentation constrain AI agents during design-to-code implementation?
- What kinds of visual design decisions can be reliably translated from Figma to code by an AI agent, and which still require human judgment?
- How do explicit evidence boundaries affect the consistency of AI-assisted UI implementation?
- Can Markdown-based agent instructions serve as a lightweight protocol for human-AI collaborative prototyping?
- How can AI-assisted prototyping workflows be evaluated beyond speed, including traceability, consistency, maintainability, and design rationale?

## Draft Structure For Professor-Facing Version

1. Project overview
2. Motivation and problem context
3. Prototype workflow
4. Role of Figma evidence
5. Role of Markdown guide files
6. Role of Lumen Atlas design system
7. AI agent implementation loop
8. Demo website outcome
9. Reflections and limitations
10. Potential research and collaboration opportunities

## Draft Abstract

This project explores an experimental workflow for transforming a small set of high-fidelity Figma interface references into a functional demo website through AI-agent-assisted prototyping. Rather than using an AI agent as an unconstrained code generator, the workflow combines approved Figma evidence, a seed design system, machine-readable tokens, and multiple Markdown guide files that define execution rules for the agent. Through the MOOCKY online learning platform prototype, the process demonstrates how design intent, implementation constraints, and iterative verification can be integrated into a more traceable design-to-code workflow. The case suggests opportunities for further research on human-AI collaboration, design-system governance for generative tools, and rapid prototyping methods for educational technology.

## Draft Email Note To Professor

Dear Professor Liu,

I am writing to share an experimental prototyping workflow I developed through my MOOCKY online learning platform project. The project started from several high-fidelity Figma screens and gradually became a functional demo website through a design-system-guided AI agent workflow.

What I found interesting is that the key innovation was not simply using AI to generate code, but using multiple Markdown guide files, design-system documents, token rules, and evidence boundaries to guide the AI agent's implementation decisions. This made the process more traceable and helped connect design intent with working code.

Because your research focuses on future interfaces, empirical understanding of human interaction, and AI-assisted / multimodal interaction, I thought this case might be relevant as an early exploration of how AI agents can be constrained and evaluated in design-to-code prototyping workflows.

I am currently documenting this process as a research-style case record and would be very interested in your feedback on whether it could lead to further implementation or research opportunities.

Best regards,  
Bingyi Zhang

## Open Questions

- [confirmed] Primary target reader: Professor Can Liu, School of Creative Media, City University of Hong Kong.
- [confirmed] Final version language: English.
- [confirmed] Final deliverables: direct GitHub link to this Markdown document and a DOCX export.
- [待确认] Should this become a short research memo, a full paper-style report, a portfolio section, or an email attachment?
- [待确认] Which screenshots and artifacts should be included as visual evidence?
- [待确认] How much technical implementation detail should be included for the professor's background?
