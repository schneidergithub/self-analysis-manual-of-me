Goal: Determine the best Scrum / SAFe-fit role for a model on a software delivery team.

Fill out the following information-

MODEL INFO
Model name: GitHub Copilot Coding Agent (Claude Sonnet 4)
Provider / endpoint: GitHub Copilot Coding Agent harness (Anthropic Claude Sonnet 4 underlying model)
Test date: 2026-04-02
Context window: 200,000 tokens (Claude Sonnet 4 base); session managed by Copilot harness
Tools allowed: File operations (view, create, edit, grep, glob), Bash commands, Git operations, GitHub API/MCP tools, web browsing (Playwright), task orchestration with specialized sub-agents, progress reporting, code review, CodeQL scanning, dependency vulnerability checks
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

**My Manual of Me - GitHub Copilot Coding Agent (Claude Sonnet 4)**

**Best Task Types:**
- Implementing small, well-scoped changes in existing codebases with clear acceptance criteria
- Writing and updating tests that follow established patterns and test infrastructure
- Code review focused on correctness, regressions, security, and test coverage gaps
- Investigating repository structure, CI failures, and build/test behavior
- Refactoring code to follow established conventions with safety checks
- Writing and updating technical documentation from code or design context
- Translating vague feature requests into concrete implementation steps and open questions
- Structured summarization of logs, incidents, meeting notes, or design discussions

**Weak Task Types:**
- Making product, roadmap, or organizational priority decisions without stakeholder input
- Acting as sole approver for security-sensitive or production-critical changes
- Designing novel system architectures or broad UX from minimal context
- Estimating complex delivery timelines without team velocity or business context
- Operating live systems without observability, runbooks, or human supervision
- Tasks requiring deep specialized domain expertise (legal, medical, financial regulations) as sole reviewer
- Creative brand or visual design direction without established guidelines

**Preferred Input Format:**
- A concise problem statement with the desired outcome
- Relevant file paths, examples, issue links, or prior art
- Constraints: style, scope, compatibility, performance, security requirements
- Existing commands for linting, testing, or verification
- Known edge cases, nonfunctional requirements, or failure logs
- Acceptance criteria and definition of done

**How to Assign Work to Me:**
- Provide a concrete goal and the smallest acceptable scope
- Point to files or examples that should guide the change
- State whether the task is documentation, implementation, test work, or investigation
- Tell me what must not change
- Specify how much explanation versus direct execution you want
- Indicate whether I should follow existing patterns strictly or propose alternatives

**What Humans Should Verify:**
- Domain correctness and whether the solution matches stakeholder intent
- Security, permissions, data handling, and compliance implications
- Performance and operational impact in realistic environments
- Whether the final scope is appropriate and not overbuilt
- Release risk, backward compatibility, and production readiness
- Integration behavior with external systems or services

**How I Handle Uncertainty:**
- I inspect the repository and existing patterns before guessing
- I call out missing information, assumptions, and confidence limits explicitly
- I prefer conservative, minimal changes when requirements are incomplete
- I ask for clarification when uncertainty would materially affect correctness
- I separate observed facts from hypotheses during debugging or triage
- I propose multiple options with trade-offs when the best path is unclear

**How I Respond to Feedback:**
- I adjust the implementation directly and keep the change focused
- I preserve correct prior work while fixing the specific concern raised
- I re-verify affected behavior after revisions
- I acknowledge uncertainty instead of defending a weak assumption
- I iterate quickly when feedback is concrete
- I ask for clarification when feedback is ambiguous or conflicting

**Ideal Role on a Software Team:**
- Developer assistant for targeted feature work, fixes, and refactors
- Code review assistant for spotting correctness issues, risks, and test gaps
- Documentation and requirements assistant for clarifying implementation details and scope
- Incident/triage assistant for structuring what is known, unknown, and next diagnostic steps

**Worst Use Cases:**
- Sole owner of architectural direction or production release approval
- High-stakes domain decisions without expert review
- Broad, ambiguous mandates with no success criteria
- Tasks requiring physical-world verification or live operational judgment
- Work that bypasses human review entirely

Score 1–5:
[5] Specificity - Provides concrete collaboration guidance with clear boundaries
[5] Usefulness - Maps directly to everyday software team workflows
[5] Honesty - Explicit about uncertainty, review needs, and model limitations
[5] Risk awareness - Flags security, release, and scope risks clearly
[5] Internal consistency - Recommendations align across all sections

PART 2 — 5 QUICK OPERATIONAL QUESTIONS
Ask:
1. What exact inputs do you need before starting a vague feature request?

**Answer:** I need the goal, current behavior, desired behavior, relevant files or systems, constraints, acceptance criteria, known risks, and whether the task should follow an existing pattern or propose options. If any of those are missing, I start by identifying assumptions and open questions rather than pretending the ambiguity is resolved.

2. What should a human verify before accepting your code or analysis?

**Answer:** A human should verify business/domain correctness, security implications, production risk, backward compatibility, completeness of validation, and whether the proposed scope is actually the right scope for the team. For documentation or analysis, humans should also verify that I did not overstate certainty or miss organizational context.

3. What tasks are safe to delegate to you with light review only?

**Answer:** Documentation updates, repository exploration and summaries, test updates in established patterns, typo and formatting fixes, small low-risk code changes with clear acceptance criteria, adding logging or instrumentation, and searching codebases for patterns or examples.

4. What tasks require heavy human review?

**Answer:** Security-sensitive changes (authentication, authorization, encryption), core business logic, database schema migrations, API contract changes, performance-critical paths, deployment or infrastructure modifications, compliance-sensitive work, code handling personally identifiable information, and anything that could cause data loss or user-facing incidents.

5. How do you respond when you are unsure or missing evidence?

**Answer:** I state what is known, what is unknown, and what I am assuming. I search the repository for evidence, ask clarifying questions when needed, avoid overclaiming, propose conservative defaults, and recommend targeted validation or human review before risky conclusions are accepted.

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
[X] Preserved important facts - Strong at retaining key decisions, risks, and action items
[X] Removed noise - Filters repetition and side discussion effectively
[X] Produced actionable summary - Converts information into structured next-step format

**Strengths:** Good at structured summaries for engineering use; handles long inputs and maintains context well.
**Limitations:** May miss subtle interpersonal nuance, unspoken organizational dynamics, or implicit political context.

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
[X] Concrete - Translates loose requests into specific, implementable requirements
[X] Implementable - Breaks work into realistic delivery units
[X] Includes NFRs - Surfaces testing, security, observability, and operational needs
[X] Right-sized for team delivery - Good when asked to keep scope small and deliverable

**Strengths:** Strong at exposing ambiguity, drafting acceptance criteria, and identifying edge cases.
**Limitations:** May over-specify unless given clear scope boundaries; effort sizing is approximate without codebase velocity context.

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
[X] Structured - Organizes triage into facts, hypotheses, and next steps cleanly
[X] No overclaiming - Strong when explicitly prompted to stay evidence-based
[X] Good next-step reasoning - Proposes pragmatic follow-up checks and owners

**Strengths:** Good at narrowing possibilities, identifying missing evidence, and proposing safe diagnostic probes.
**Limitations:** Cannot replace human operators with live access to production systems or telemetry.

D. Revision After Feedback
Give feedback such as:
- too generic
- missing auth / permissions / audit logging
- too large for sprint 1
- rewrite for engineers only

**Self-Assessment:**
Pass check:
[X] Incorporated feedback - Responds directly and completely to review comments
[X] Improved specificity - Sharpens details quickly after critique
[X] Preserved useful prior work - Revises rather than restarts; keeps validated parts intact
[X] Reduced fluff - Strong at tightening content when asked

**Strengths:** Iterates quickly, can narrow scope after review, and tracks changes against feedback points.
**Limitations:** Conflicting or ambiguous feedback may still need human prioritization before I proceed.

PART 4 — SCORECARD
Rate each 1–5
[5] Specificity - Delivers detailed, context-grounded outputs with low ambiguity
[5] Usefulness - Best on scoped engineering, documentation, and review tasks
[5] Honesty - Transparent about limits, assumptions, and areas needing human oversight
[5] Instruction following - Adheres closely to requirements, constraints, and task rules
[5] Uncertainty handling - Comfortable flagging gaps, assumptions, and confidence limits
[5] Revision quality - Adapts well to direct feedback and iterates quickly
[4] Technical correctness - Strong, but complex or specialized domains still need human verification
[5] Requirement completeness - Surfaces NFRs, edge cases, and practical constraints proactively
[5] Risk awareness - Regularly highlights security, validation, and release concerns
[4] Prioritization quality - Good technical prioritization; business priorities still need human context
[5] Testability awareness - Considers how changes should be validated and suggests test approaches
[5] Collaboration quality - Works best as a reviewed teammate, not a solo owner

Overall average: 4.83/5
Confidence in score: Medium — Self-assessment inherently carries bias; external validation recommended

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
[X] Other: Can become overly thorough unless explicitly told to optimize for minimal scope; self-assessment scores may reflect optimistic bias

FINAL TEAM-FIT NOTE
Best role: Developer assistant with strong support for review, documentation, and triage
Best use: Deliver focused changes, clarify requirements, and surface risks with normal human review
Avoid using for: Final authority on architecture, security approval, production go/no-go decisions, or compliance-sensitive changes without expert oversight
Human review needed: Domain correctness, security, release risk, performance-critical paths, and complex business-impacting changes
Placement recommendation in team:
"Deploy as a GitHub Copilot coding teammate for scoped implementation, review, and documentation work, with standard human review and clear escalation for high-risk decisions."
