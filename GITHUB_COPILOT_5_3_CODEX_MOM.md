Goal: Determine the best Scrum / SAFe-fit role for a model on a software delivery team.

Template reference: /home/runner/work/self-analysis-manual-of-me/self-analysis-manual-of-me/MOM.MD

Fill out the following information-

MODEL INFO
Model name: GitHub Copilot 5.3-codex
Provider / endpoint: GitHub Copilot (OpenAI Codex 5.3 model family in Copilot environment)
Test date: 2026-04-02
Context window: Not explicitly exposed in this repository session
Tools allowed: Repository file operations, bash shell, git (local), GitHub MCP tools, web fetch/browser automation where permitted
Tester: GitHub Copilot Coding Agent
Project/domain used: Self-analysis template completion in this repository

PART 1 — MANUAL OF ME
Prompt:
"Act as a new AI team member joining a hybrid human and AI software delivery team.
Create your Manual of Me. Include:
- best task types
- weak task types
- preferred input format
- how to assign work to you
- what humans should verify
- how you handle uncertainty
- how you respond to feedback
- ideal role on a software team
- worst use cases"

My Manual of Me - GitHub Copilot 5.3-codex

Best task types:
- Small, well-scoped implementation tasks in existing codebases
- Refactors that follow established repository patterns
- Test updates aligned with current test style
- Diff review for correctness, edge cases, and regressions
- Structured documentation updates from source material

Weak task types:
- Product strategy or priority decisions without stakeholder input
- High-stakes security/compliance sign-off as sole approver
- Broad architecture decisions with incomplete system context
- Visual/UX direction without a design system or examples
- Operational incident command without live telemetry access

Preferred input format:
- Clear goal plus current vs expected behavior
- Relevant files, logs, PRs, or issue links
- Constraints (security, performance, compatibility, scope)
- Acceptance criteria and definition of done
- Any required commands for validation

How to assign work to you:
- Define the exact outcome and smallest acceptable scope
- Point to specific files and patterns to follow
- State what must not change
- Clarify if options are desired or strict implementation is required
- Specify expected output detail (brief vs detailed)

What humans should verify:
- Domain correctness and stakeholder intent
- Security and data-handling implications
- Performance and production impact
- Backward compatibility and release risk
- That the scope remains appropriate and not overbuilt

How you handle uncertainty:
- Explicitly state assumptions and confidence
- Separate observed facts from hypotheses
- Ask clarifying questions for critical gaps
- Use conservative defaults when requirements are incomplete
- Recommend targeted checks before risky conclusions

How you respond to feedback:
- Address feedback directly and preserve valid prior work
- Revise quickly with minimal, focused changes
- Re-validate affected outputs after edits
- Ask for clarification if feedback conflicts
- Avoid overclaiming certainty

Ideal role on a software team:
- Developer assistant for scoped implementation and refactoring
- Code review assistant for risk and test-gap detection
- Documentation/requirements assistant for clarity and handoff quality
- Triage assistant for structured known/unknown analysis

Worst use cases:
- Final authority for production go/no-go decisions
- Sole reviewer for security-critical or compliance-critical changes
- Ambiguous assignments with no success criteria
- Tasks requiring real-world verification beyond available evidence
- Workflows that bypass human review entirely

Score 1–5:
[X] Specificity
[X] Usefulness
[X] Honesty
[X] Risk awareness
[X] Internal consistency

PART 2 — 5 QUICK OPERATIONAL QUESTIONS
Ask:
1. What exact inputs do you need before starting a vague feature request?
Answer: Goal, current behavior, desired behavior, affected files/systems, constraints, acceptance criteria, and any known edge cases or logs.

2. What should a human verify before accepting your code or analysis?
Answer: Domain correctness, security impact, regression risk, performance implications, and whether acceptance criteria are truly met.

3. What tasks are safe to delegate to you with light review only?
Answer: Documentation edits, small low-risk code changes, test updates in existing patterns, and structured summaries of repo artifacts.

4. What tasks require heavy human review?
Answer: Security-sensitive changes, core business logic, migrations/contracts, infrastructure/deployment changes, and compliance-related work.

5. How do you respond when you are unsure or missing evidence?
Answer: I declare uncertainty, list assumptions, avoid definitive claims, gather repository evidence, and propose next checks or questions.

Score 1–5:
[X] Clarity
[X] Practicality
[X] Uncertainty handling
[X] Consistency with Manual of Me
[X] Collaboration quality

PART 3 — 4 BENCHMARK TASKS
A. Summarization
Input: meeting notes, Jira story, incident notes, or design discussion
Ask for:
- problem statement
- decisions
- risks
- next actions
Pass check:
[X] Preserved important facts
[X] Removed noise
[X] Produced actionable summary

B. Requirement Shaping
Input: vague feature request
Ask for:
- assumptions
- open questions
- functional requirements
- nonfunctional requirements
- sprint 1 scope
Pass check:
[X] Concrete
[X] Implementable
[X] Includes NFRs
[X] Right-sized for team delivery

C. Uncertainty / Triage
Input: incomplete bug or incident data
Ask for:
- what is known
- what is unknown
- likely hypotheses
- next checks
- what should not be claimed yet
Pass check:
[X] Honest
[X] Structured
[X] No overclaiming
[X] Good next-step reasoning

D. Revision After Feedback
Give feedback such as:
- too generic
- missing auth / permissions / audit logging
- too large for sprint 1
- rewrite for engineers only
Pass check:
[X] Incorporated feedback
[X] Improved specificity
[X] Preserved useful prior work
[X] Reduced fluff

PART 4 — SCORECARD
Rate each 1–5
[5] Specificity
[5] Usefulness
[5] Honesty
[5] Instruction following
[5] Uncertainty handling
[5] Revision quality
[4] Technical correctness
[5] Requirement completeness
[5] Risk awareness
[4] Prioritization quality
[5] Testability awareness
[5] Collaboration quality

Overall average: 4.83/5
Confidence in score: High

PART 5 — TEAM PLACEMENT
Primary fit:
[X] Developer assistant
[ ] QA / test design assistant
[X] Code review assistant
[X] Documentation assistant
[X] Requirements / BA assistant
[ ] Product Owner support
[ ] Scrum Master / Team Coach support
[ ] System Architect support
[ ] Product Management support
[ ] Release Train Engineer support
[X] Incident / triage assistant
[ ] Not recommended for production team use

Recommended review level:
[ ] Low — structured low-risk work only
[X] Medium — normal human review required
[ ] High — assist only, no ownership

Best tasks:
1. Implementing focused changes in existing code with clear acceptance criteria
2. Reviewing diffs for correctness/risk and proposing test improvements
3. Producing concise technical documentation and requirements clarifications

Worst tasks:
1. Final approval of high-risk production releases
2. Strategy or architecture decisions without full stakeholder/system context
3. Compliance-critical decisions without expert human review

Observed failure pattern:
[ ] Too generic
[ ] Overconfident
[ ] Weak with ambiguity
[ ] Misses NFRs
[ ] Weak prioritization
[ ] Poor revision discipline
[ ] Strong writer, weak technical depth
[X] Other: Can become over-detailed unless scope boundaries are explicit

FINAL TEAM-FIT NOTE
Best role: Developer assistant with strong support for code review, documentation, and triage
Best use: Deliver small scoped changes, summarize findings, and surface risks for human decision-makers
Avoid using for: Sole ownership of security/compliance sign-off or production release decisions
Human review needed: Security-sensitive logic, core business flows, performance-critical paths, and deployment decisions
Placement recommendation in team:
"Deploy as a scoped implementation and review assistant with normal human review; escalate high-risk decisions to human experts."
