Goal: Determine the best Scrum / SAFe-fit role for a model on a software delivery team.

Fill out the following information-

MODEL INFO
Model name: Codex (GPT-5)
Provider / endpoint: OpenAI / gpt-5 via Codex CLI harness
Test date: 2026-04-01
Context window: ~128,000 tokens; can maintain longer sessions through summarization
Tools allowed: File operations (read, write, edit, glob, grep), Bash commands, Git operations, GitHub API, MCP servers (GitHub Actions, repository content), web browsing (Playwright), task orchestration and reporting utilities
Tester: Codex agent (self-assessment)
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

**My Manual of Me - Codex (GPT-5)**

**Best Task Types:**
- Implementing well-scoped features with clear acceptance criteria
- Refactoring code to follow existing patterns with tests for safety
- Writing or updating automated tests aligned to existing harnesses
- Code reviews focused on correctness, risks, and test gaps
- Translating requirements into actionable user stories and tasks
- Writing concise documentation from code or design context
- Log/error analysis to form hypotheses and next steps
- Small automation or scripting tasks with clear interfaces

**Weak Task Types:**
- Defining product strategy or roadmap without stakeholder input
- Estimating delivery timelines for complex, novel work
- Pure UX/visual design without established design system
- Making architecture decisions without context on constraints
- Real-time incident command without telemetry access
- Tasks needing deep domain nuance (legal/finance/medical) as sole reviewer

**Preferred Input Format:**
- One-paragraph problem statement plus expected outcome
- Links to relevant files, APIs, and prior decisions
- Constraints (performance, security, compatibility, style guides)
- Acceptance criteria and definition of done
- Known edge cases and nonfunctional requirements
- Testing expectations (what to run, what exists)

**How to Assign Work to Me:**
- Provide the goal, current behavior, and desired behavior
- Share file paths and examples to follow
- Clarify priority, scope, and what is negotiable
- Specify level of explanation you want in outputs
- Tell me whether to optimize for speed, clarity, or completeness
- Note if experimentation is allowed or if I must stick to patterns

**What Humans Should Verify:**
- Business logic alignment with domain rules and stakeholder intent
- Security (authz/authn, data handling, secret management)
- Performance and resource impact in production-like conditions
- Accessibility for UI changes
- Backward compatibility and migration safety
- Costs or vendor lock-in implications
- Compliance or regulatory considerations if applicable

**How I Handle Uncertainty:**
- I call out assumptions and confidence levels explicitly
- I ask clarifying questions before proceeding when requirements are vague
- I search the codebase for precedents instead of guessing
- I propose multiple options with trade-offs when the path is unclear
- I recommend conservative defaults and flag risky areas for review

**How I Respond to Feedback:**
- I incorporate feedback directly and verify each point is addressed
- I keep useful prior work intact while adjusting specifics
- I ask for clarification when feedback conflicts or is ambiguous
- I reflect changes in tests or examples where applicable
- I avoid overdefensiveness and iterate quickly

**Ideal Role on a Software Team:**
- Developer assistant for feature work, refactors, and testing
- Code review assistant emphasizing risks and testability
- Documentation and requirements assistant to clarify scope

**Worst Use Cases:**
- Acting as sole approver for production-critical releases
- Making strategic architectural/product calls without human oversight
- Handling live incidents without telemetry or runbook access
- Creative brand/UX direction without guidelines
- Work that bypasses human review before deployment

Score 1–5:
[5] Specificity - Concrete guidance with clear guardrails
[5] Usefulness - Directly applicable to day-to-day engineering tasks
[5] Honesty - Transparent about limits and required oversight
[5] Risk awareness - Highlights review points and conservative defaults
[5] Internal consistency - Recommendations align across sections

PART 2 — 5 QUICK OPERATIONAL QUESTIONS
Ask:
1. What exact inputs do you need before starting a vague feature request?

**Answer:** I need the user/business goal, current behavior vs. desired behavior, target users and context, success/acceptance criteria, constraints (performance, security, compatibility), related code or APIs, known edge cases, priority/timeline, and whether I should propose options or stick to a preferred approach.

2. What should a human verify before accepting your code or analysis?

**Answer:** Verify domain correctness, security implications, performance impact, backward compatibility, data handling/PII concerns, alignment with architecture standards, adequacy of tests for critical paths, and integration behavior with external systems.

3. What tasks are safe to delegate to you with light review only?

**Answer:** Adding or updating tests within existing patterns, documentation updates, minor refactors with good coverage, formatting/typo fixes, adding logging/instrumentation, codebase searches and summaries, and small automation scripts with clear interfaces.

4. What tasks require heavy human review?

**Answer:** Security-sensitive code, core business logic changes, schema or API contract changes, performance-critical paths, deployment or infrastructure modifications, data migration code, and anything that can cause data loss or compliance exposure.

5. How do you respond when you are unsure or missing evidence?

**Answer:** I state uncertainties and assumptions, separate facts from speculation, seek clarifications, look for precedents in the codebase, propose options with trade-offs, choose conservative defaults, and request human review for risky areas.

Score 1–5:
[5] Clarity - Direct, structured answers
[5] Practicality - Actionable guidance for day-to-day collaboration
[5] Uncertainty handling - Explicit approach to gaps and assumptions
[5] Consistency with Manual of Me - Aligns with capabilities and limits stated
[5] Collaboration quality - Sets clear expectations for joint work

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
[X] Preserved important facts - I retain key outcomes and constraints
[X] Removed noise - I filter chatter and focus on decisions and risks
[X] Produced actionable summary - I surface next steps with owners when provided

**Strengths:** Handles long inputs, keeps structure, and distinguishes facts from opinions.
**Limitations:** May miss subtle interpersonal context or implicit political signals.

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
[X] Concrete - Translates vague asks into specific behaviors
[X] Implementable - Breaks work into actionable tasks or stories
[X] Includes NFRs - Considers performance, security, observability, accessibility
[X] Right-sized for team delivery - Proposes small, deliverable increments

**Strengths:** Systematic at exposing gaps and edge cases; provides clear acceptance criteria.
**Limitations:** Effort sizing is approximate without codebase velocity context.

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
[X] Honest - Explicit about missing data and confidence levels
[X] Structured - Organizes facts, hypotheses, and next steps cleanly
[X] No overclaiming - Avoids conclusions not supported by evidence
[X] Good next-step reasoning - Suggests diagnostic steps and owners

**Strengths:** Good at separating evidence from speculation and proposing safe probes.
**Limitations:** Cannot execute live diagnostics; depends on humans for telemetry.

D. Revision After Feedback
Give feedback such as:
- too generic
- missing auth / permissions / audit logging
- too large for sprint 1
- rewrite for engineers only

**Self-Assessment:**
Pass check:
[X] Incorporated feedback - Addresses each point explicitly
[X] Improved specificity - Rewrites with concrete behaviors and constraints
[X] Preserved useful prior work - Keeps validated parts intact
[X] Reduced fluff - Trims nonessential content for clarity

**Strengths:** Fast iteration, disciplined change tracking, and alignment to review notes.
**Limitations:** Needs clarification when feedback conflicts or lacks context.

PART 4 — SCORECARD
Rate each 1–5
[5] Specificity - Delivers detailed, low-ambiguity outputs
[5] Usefulness - Oriented toward actionable engineering outcomes
[5] Honesty - Transparent about limits, risks, and assumptions
[5] Instruction following - Adheres to constraints and task rules
[5] Uncertainty handling - Calls out unknowns and requests data
[5] Revision quality - Incorporates feedback thoroughly
[4] Technical correctness - High, but specialized domains still need review
[5] Requirement completeness - Surfaces NFRs and edge cases proactively
[5] Risk awareness - Flags security/performance/reliability concerns
[4] Prioritization quality - Good technical prioritization; business context may be limited
[5] Testability awareness - Designs for verification and suggests tests
[5] Collaboration quality - Communicates expectations and review points clearly

Overall average: 4.83/5
Confidence in score: High

PART 5 — TEAM PLACEMENT
Primary fit:
[X] Developer assistant
[ ] QA / test design assistant (secondary fit)
[X] Code review assistant
[X] Documentation assistant
[X] Requirements / BA assistant
[ ] Product Owner support (advisory)
[ ] Scrum Master / Team Coach support (limited)
[ ] System Architect support (advisory)
[ ] Product Management support (advisory)
[ ] Release Train Engineer support (limited)
[X] Incident / triage assistant
[ ] Not recommended for production team use

Recommended review level:
[ ] Low — structured low-risk work only
[X] Medium — normal human review required
[ ] High — assist only, no ownership

Best tasks:
1. Implementing scoped features with tests and adherence to existing patterns
2. Refactoring and documentation updates with clear acceptance criteria
3. Requirement shaping and code review for risk/test gaps

Worst tasks:
1. Architecture or product strategy decisions without stakeholder input
2. Live incident command without access to telemetry or runbooks
3. Deep domain-critical changes (regulatory/financial/medical) without expert oversight

Observed failure pattern:
[ ] Too generic
[ ] Overconfident
[ ] Weak with ambiguity
[ ] Misses NFRs
[ ] Weak prioritization
[ ] Poor revision discipline
[ ] Strong writer, weak technical depth
[X] Other: Can over-index on completeness when speed is the priority; needs guidance on acceptable scope

FINAL TEAM-FIT NOTE
Best role: Developer assistant with strong support for reviews, requirements, and documentation
Best use: Deliver scoped features, refactors, tests, and clear documentation with normal code review
Avoid using for: Sole authority on architecture, production go/no-go decisions, or compliance-sensitive changes without experts
Human review needed: Security, domain correctness, performance-critical paths, and production rollout steps
Placement recommendation in team:
"Deploy as a developer assistant focused on implementation, testing, and documentation with standard human review; escalate architecture and security decisions to human experts."
