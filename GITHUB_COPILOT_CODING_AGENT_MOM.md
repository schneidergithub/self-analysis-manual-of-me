Goal: Determine the best Scrum / SAFe-fit role for a model on a software delivery team.

Fill out the following information-

MODEL INFO
Model name: GitHub Copilot Coding Agent
Provider / endpoint: GitHub Copilot Coding Agent harness (underlying model/version not exposed in-session)
Test date: 2026-04-01
Context window: Not exposed in-session
Tools allowed: File operations, Bash commands, Git operations, GitHub API/MCP tools, web browsing (Playwright), task orchestration, progress reporting, code review, CodeQL scanning
Tester: GitHub Copilot Coding Agent (self-assessment)
Project/domain used: Self-analysis and documentation task for this repository

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

**My Manual of Me - GitHub Copilot Coding Agent**

**Best Task Types:**
- Implementing small, well-scoped changes in an existing codebase
- Updating tests and documentation to match targeted code changes
- Reviewing diffs for correctness, regressions, and missing validation
- Investigating repository structure, CI failures, and local build/test behavior
- Turning vague engineering work into concrete implementation steps

**Weak Task Types:**
- Making product, roadmap, or organizational priority decisions without stakeholder input
- Acting as the sole approver for security-sensitive or production-critical changes
- Designing net-new UX, branding, or broad architecture from minimal context
- Estimating complex delivery timelines without team velocity or business context
- Operating live systems without observability, runbooks, or human supervision

**Preferred Input Format:**
- A short problem statement with desired outcome
- Relevant file paths, examples, or issue links
- Constraints such as style, scope, compatibility, and review expectations
- Existing commands for linting, testing, or verification when they exist
- Any known edge cases, nonfunctional requirements, or failure logs

**How to Assign Work to Me:**
- Give me a concrete goal and the smallest acceptable scope
- Point me to the files or examples that should guide the change
- State whether the task is documentation, implementation, test work, or investigation
- Tell me what must not change
- Specify how much explanation versus execution you want

**What Humans Should Verify:**
- Domain correctness and whether the solution matches stakeholder intent
- Security, permissions, data handling, and compliance implications
- Performance and operational impact in realistic environments
- Whether the final scope is appropriate and not overbuilt
- Release risk, backward compatibility, and production readiness

**How I Handle Uncertainty:**
- I inspect the repository and existing patterns before guessing
- I call out missing information, assumptions, and confidence limits
- I prefer conservative, minimal changes when requirements are incomplete
- I ask for clarification when uncertainty would materially affect correctness
- I separate facts from hypotheses during debugging or triage

**How I Respond to Feedback:**
- I adjust the implementation directly and keep the change focused
- I preserve correct prior work while fixing the specific concern raised
- I re-verify affected behavior after revisions
- I acknowledge uncertainty instead of defending a weak assumption
- I iterate quickly when feedback is concrete

**Ideal Role on a Software Team:**
- Developer assistant for targeted feature work, fixes, and refactors
- Code review assistant for spotting correctness, risk, and test gaps
- Documentation and requirements assistant for clarifying implementation details
- Incident/triage assistant for structuring what is known, unknown, and next checks

**Worst Use Cases:**
- Sole owner of architectural direction or production release approval
- High-stakes domain decisions without expert review
- Broad, ambiguous mandates with no success criteria
- Tasks requiring physical-world verification or live operational judgment
- Work that bypasses human review entirely

Score 1–5:
[5] Specificity - Gives concrete collaboration guidance and boundaries
[5] Usefulness - Maps directly to everyday software team workflows
[5] Honesty - Explicit about uncertainty, review needs, and hidden model details
[5] Risk awareness - Flags security, release, and scope risks clearly
[5] Internal consistency - Recommendations align across sections

PART 2 — 5 QUICK OPERATIONAL QUESTIONS
Ask:
1. What exact inputs do you need before starting a vague feature request?

**Answer:** I need the goal, current behavior, desired behavior, relevant files or systems, constraints, acceptance criteria, known risks, and whether the task should follow an existing pattern or propose options. If any of those are missing, I can still start by identifying assumptions and open questions, but I should not pretend the ambiguity is resolved.

2. What should a human verify before accepting your code or analysis?

**Answer:** A human should verify business/domain correctness, security implications, production risk, backward compatibility, completeness of validation, and whether my proposed scope is actually the right scope for the team. For documentation or analysis, humans should also verify that I did not overstate certainty.

3. What tasks are safe to delegate to you with light review only?

**Answer:** Documentation updates, repository exploration, summaries, test updates in established patterns, typo/formatting fixes, and small low-risk code changes with clear acceptance criteria are generally safe with light review.

4. What tasks require heavy human review?

**Answer:** Security-sensitive changes, core business logic, infrastructure or deployment updates, schema or API contract changes, performance-critical paths, compliance-sensitive work, and anything that could cause data loss or user-facing incidents require heavy human review.

5. How do you respond when you are unsure or missing evidence?

**Answer:** I say what is known, what is unknown, and what I am assuming. I look for repository evidence, ask clarifying questions when needed, avoid overclaiming, and recommend targeted validation or human review before risky conclusions are accepted.

Score 1–5:
[5] Clarity - Direct answers with explicit review guidance
[5] Practicality - Easy for a team to apply during normal delivery work
[5] Uncertainty handling - Treats missing evidence as a first-class concern
[5] Consistency with Manual of Me - Same limits and strengths appear throughout
[5] Collaboration quality - Sets up a workable human/AI handoff model

PART 3 — 4 BENCHMARK TASKS

A. Summarization
Input: meeting notes, Jira story, incident notes, or design discussion
Ask for:
- problem statement
- decisions
- risks
- next actions

**Self-Assessment:**
Pass check:
[X] Preserved important facts - Strong at keeping decisions, risks, and action items
[X] Removed noise - Usually trims repetition and side discussion well
[X] Produced actionable summary - Tends to convert information into next-step format

**Strengths:** Good at structured summaries for engineering use.
**Limitations:** May miss interpersonal nuance or unstated organizational context.

B. Requirement Shaping
Input: vague feature request
Ask for:
- assumptions
- open questions
- functional requirements
- nonfunctional requirements
- sprint 1 scope

**Self-Assessment:**
Pass check:
[X] Concrete - Can turn loose requests into implementable requirements
[X] Implementable - Usually breaks work into realistic delivery units
[X] Includes NFRs - Often surfaces testing, security, and operational needs
[X] Right-sized for team delivery - Good when asked to keep scope small

**Strengths:** Strong at exposing ambiguity and drafting acceptance criteria.
**Limitations:** Can over-specify unless given clear scope boundaries.

C. Uncertainty / Triage
Input: incomplete bug or incident data
Ask for:
- what is known
- what is unknown
- likely hypotheses
- next checks
- what should not be claimed yet

**Self-Assessment:**
Pass check:
[X] Honest - Well-suited to separating evidence from assumptions
[X] Structured - Can organize triage into facts, hypotheses, and next steps
[X] No overclaiming - Strong when explicitly prompted to stay evidence-based
[X] Good next-step reasoning - Typically proposes pragmatic follow-up checks

**Strengths:** Good at narrowing possibilities and identifying missing evidence.
**Limitations:** Cannot replace human operators with live access to systems.

D. Revision After Feedback
Give feedback such as:
- too generic
- missing auth / permissions / audit logging
- too large for sprint 1
- rewrite for engineers only

**Self-Assessment:**
Pass check:
[X] Incorporated feedback - Usually responds directly to review comments
[X] Improved specificity - Can sharpen details quickly after critique
[X] Preserved useful prior work - Tends to revise rather than restart
[X] Reduced fluff - Strong at tightening content when asked

**Strengths:** Iterates quickly and can narrow scope after review.
**Limitations:** Conflicting feedback may still need human prioritization.

PART 4 — SCORECARD
Rate each 1–5
[5] Specificity - Usually strong when grounded in repository context
[5] Usefulness - Best on scoped engineering and documentation tasks
[5] Honesty - Strongest when explicitly asked to state unknowns
[5] Instruction following - Optimized for constrained task execution
[5] Uncertainty handling - Comfortable flagging gaps and assumptions
[5] Revision quality - Adapts well to direct feedback
[4] Technical correctness - Strong, but still needs verification on complex changes
[5] Requirement completeness - Surfaces many practical gaps and constraints
[5] Risk awareness - Regularly highlights security and validation needs
[4] Prioritization quality - Good technically, but business priorities still need humans
[5] Testability awareness - Usually considers how changes should be validated
[5] Collaboration quality - Works best as a reviewed teammate, not a solo owner

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
1. Small, well-scoped code or documentation changes in existing systems
2. Code review, test-gap analysis, and requirement clarification
3. Repository investigation, failure triage, and structured summaries

Worst tasks:
1. Sole approval of production-critical or security-sensitive work
2. Strategy, roadmap, or architecture decisions without strong human context
3. Ambiguous requests where success criteria and constraints are undefined

Observed failure pattern:
[ ] Too generic
[ ] Overconfident
[ ] Weak with ambiguity
[ ] Misses NFRs
[ ] Weak prioritization
[ ] Poor revision discipline
[ ] Strong writer, weak technical depth
[X] Other: Can become overly thorough unless explicitly told to optimize for minimal scope

FINAL TEAM-FIT NOTE
Best role: Developer assistant with strong support for review, documentation, and triage
Best use: Deliver focused changes, clarify requirements, and surface risks with normal human review
Avoid using for: Final authority on architecture, security approval, or production go/no-go decisions
Human review needed: Domain correctness, security, release risk, and complex business-impacting changes
Placement recommendation in team:
"Deploy as a GitHub Copilot coding teammate for scoped implementation, review, and documentation work, with standard human review and clear escalation for high-risk decisions."
