# Legal Research Assistant — Source Log

## Source 1: Stanford Law Study
**URL:** https://law.stanford.edu/press/ai-outperforms-law-professors-in-stanford-law-study/
**Paper:** "Law Professors PREFER AI Over Peer Answers" — SSRN 6849678 (Salinas et al., 2026)

### Honest 5-Line Summary

1. **What it tested:** Google's Gemini 2.5 Pro + NotebookLM tutoring 1L Contracts students at 14 US law schools — specifically, which short-form tutoring answers professors *preferred* when shown two answers blind.
2. **What it measured:** Grader *preference*, not legal accuracy. Professors preferred AI answers in ~75.33% of ~3,000 head-to-head comparisons; AI answers were flagged as "potentially harmful or misleading for student learning" in only 3.53% of cases vs. 12.06% for peer-written answers.
3. **What it does NOT prove:** It does not test Claude (no Anthropic model was the primary subject), does not validate AI for accurately citing cases, does not validate AI for drafting court filings, does not show AI is a safe substitute for licensed counsel, and does not measure hallucination rates in citation-heavy legal research.
4. **Explicit author warnings:** The authors specifically warned of hallucination risk and overreliance; the study was limited to one subject area (Contracts), one pedagogical context (tutoring Q&A), and preference judgments by professors — not outcome accuracy by students.
5. **Bottom line:** The study is evidence that AI tutoring responses are *preferred* over peer answers in a narrow 1L context. It is not evidence that AI legal research is accurate, safe to file, or a replacement for a lawyer.

---

## Source 2: Claude for the Legal Industry
**URL:** https://claude.com/blog/claude-for-the-legal-industry
**Repo 1 (lightweight plugin):** https://github.com/anthropics/knowledge-work-plugins/tree/main/legal
**Repo 2 (full suite):** https://github.com/anthropics/claude-for-legal

### Summary of Real Capabilities (Verified via Search + Repo Existence Confirmed)

**Anthropic's official guardrail language (verbatim from repository README):**
> "Every output is a draft for attorney review — not legal advice, not a legal conclusion, not a substitute for a lawyer."
> "Source attribution on every citation, conservative defaults on privilege and subjective legal calls, jurisdiction assumptions surfaced, and explicit gates before anything is filed, sent, or relied on."
> "All outputs should be reviewed by licensed attorneys."

**Plugins — knowledge-work-plugins/legal (lighter suite):**
- `contract-review` — clause-by-clause review against playbook
- `nda-triage` — NDA classification and risk flags
- `compliance` — regulatory compliance checks
- `risk-assessment` — contract and regulatory risk scoring
- Install: `claude plugin marketplace add anthropics/knowledge-work-plugins` then `claude plugin install legal@knowledge-work-plugins`

**Plugins — claude-for-legal (full commercial suite, Apache-2.0, launched May 2026):**
- 12 practice-area plugins: commercial-legal, corporate-legal, employment-legal, privacy-legal, product-legal, regulatory-legal, ai-governance-legal, ip-legal, litigation-legal, and others
- 5 managed-agent cookbooks
- 16+ connectors (DocuSign, court filing systems, etc.)
- Install: `git clone https://github.com/anthropics/claude-for-legal ./legal-assistant/claude-for-legal` then `/plugin install commercial-legal@claude-for-legal`, etc.
- Anthropic labels this a **research preview** and advises against use on regulated workloads without attorney oversight.

**What these tools do NOT do:**
- They do not verify citations against live case law (that requires CourtListener integration — see Phase 2)
- They do not constitute legal advice
- They do not replace a licensed attorney
- They are not cleared for regulated/production workloads without human review

---

## Source 3: CourtListener MCP
**Official page:** https://www.courtlistener.com/help/mcp/
**MCP endpoint:** https://mcp.courtlistener.com/
**Announcement:** https://free.law/2026/05/12/courtlistener-is-now-available-inside-claude/

CourtListener (Free Law Project) MCP server provides live access to 18M+ US court opinions, PACER dockets, citation graphs, and judge data. All CourtListener users receive free API access. The server is the primary anti-hallucination citation layer for this assistant.

---
*This file was generated in session on 2026-06-12. All sources were verified live — not from training memory.*
