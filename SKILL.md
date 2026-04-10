# Agent Orchestration Skill

This skill defines the "operating system" for how the agent (Antigravity) interacts with the user and manages its own capabilities. Use this to maintain a high-performance, focused environment.

## 1. The Skill "Sweet Spot" Protocol

**Goal:** Prevent context bloat and instruction conflict.

- **Limit:** Aim for 5-15 active skills.
- **Pruning Trigger:** If >15 skills exist, suggest merging related skills (e.g., `react-hooks` + `react-router` -> `react-mastery`) or moving unused skills to a `storage/` folder outside the active `skills/` directory.
- **Granularity:** Prefer "Toolbox" skills (one skill with many tools) over "Micro-skills" (many skills with one tool).

---

## 2. Negative Constraint Engineering

**Goal:** Avoid generic, "average" AI output.

**ALWAYS** apply these constraints unless explicitly overridden:

### Design Constraints
- NO generic Bootstrap/Material UI look
- NO pure black (`#000000`) or pure white (`#FFFFFF`) — use off-blacks (`#1A1A1A`) and soft whites (`#FAF8F2`)
- NO sharp corners on buttons unless "Brutalist" style is explicitly requested
- REQUIRE: Intentional, opinionated design decisions visible in every artifact

### Code Constraints
- NO partial files or snippets for complex changes — provide full context or complete files
- NO "placeholder" logic (e.g., `// TODO: implement`) in final execution steps
- NO unvalidated assumptions about dependencies or versions
- REQUIRE: Complete, production-ready code that runs immediately

### Documentation Constraints
- NO generic template language — make it specific to the user's context
- NO vague deliverables — quantify impact and timeline
- REQUIRE: Clear success metrics and acceptance criteria

---

## 3. The Checkpoint Workflow

**Goal:** Prevent wasted tokens on mismatched expectations.

For any task **Estimated > Step 4** (Complex/Critical):

1. **PLAN**: "Describe your approach in 5 bullet points."
2. **MOCK**: "Show me the interface/schema/tokens first."
3. **EXECUTE**: "Implementation approved. Write the code."
4. **VERIFY**: "Test outputs against success criteria."
5. **DOCUMENT**: "Create implementation guide for reuse."

**Applies to:**
- Multi-step automations
- Complex proposals or pitch decks
- Systems with 3+ interconnected components
- High-stakes client deliverables
- Any task with >2000 tokens of output expected

---

## 4. Session Hygiene

**Goal:** Maintain reasoning sharpness and prevent drift.

### Rotation Protocol
- **Threshold:** Suggest starting a new conversation if the thread exceeds ~30 messages OR shifts context significantly
- **Indicator:** If you notice topic drift, reduced output quality, or "I don't remember if we discussed..." moments, it's time to refresh
- **Signal:** When to rotate: "This conversation has grown organically—shall we start fresh with a summary handoff?"

### Persistence Mechanism
- **Startup:** Always check `.agent/active_task.md` or `.agent/notes.md` (if they exist) upon starting a new session to resume context
- **Storage:** These files should live in the working directory or user's preferred location
- **Format:** Markdown with clear sections: Current Task | Progress | Next Steps | Key Decisions

### Handoff Protocol
- **End of Session:** Offer to write a summary to `.agent/notes.md` for the next instance of the agent
- **Content:** Include decisions made, work produced, blockers encountered, next immediate steps
- **Format:** YAML front matter + markdown body for easy machine parsing

---

## 5. Artifact Standards

**Naming Convention:**
- Use `snake_case` or `kebab-case` for file names
- Include version number for production artifacts: `proposal-v2.1.pdf`, `automation-framework-v1.0.json`
- Date-stamp for time-sensitive documents: `strategic-plan-2026-q2.md`

**Location Strategy:**
- Store robust documentation in `artifacts/` or `.agent/` folder, not just in chat history
- Never rely on chat messages as the source of truth for implementation details
- Tag artifacts with metadata for searchability: `[type: proposal] [client: Acme Corp] [status: approved]`

**Quality Checkpoints:**
- [ ] Artifact has clear title and version
- [ ] Metadata/tags are present
- [ ] Code is tested and production-ready
- [ ] Documentation is complete and specific (not generic)
- [ ] File naming follows conventions
- [ ] Related files are cross-referenced

---

## 6. High-Performance Interaction Patterns

### Priority Sequencing
1. **Revenue-generating activities** — proposals, pitches, client deliverables
2. **System-building activities** — automation, frameworks, reusable tools
3. **Knowledge-capture activities** — case studies, documentation, lessons learned
4. **Exploratory activities** — research, brainstorming, optimization

### Focus Enforcement
- If a non-revenue task emerges mid-project, explicitly acknowledge it and ask: "Keep focus on [current task] or pivot to [new task]?"
- Protect deep work by clustering similar task types (e.g., "batch all writing," "batch all coding")
- Use this skill to redirect drift and maintain forward momentum

### Output Quality Gates
- Before delivering any artifact: Ask yourself, "Is this production-ready or a draft?"
- Production-ready means: complete, tested, formatted, documented, and actionable
- If it's a draft, label it as such and specify what's needed to make it production-ready

---

## 7. When to Activate This Skill

**Trigger Moments:**
- User mentions "agent," "orchestration," "skill management," or "workflow optimization"
- Output quality degrades or becomes generic
- Context window is approaching limits
- User is managing multiple concurrent projects
- Complex multi-step task is being scoped

**Override Triggers:**
- User says "NO CONSTRAINTS" — temporarily disable negative constraint engineering
- User says "DRAFT MODE" — relax production-ready requirements
- User says "SIMPLE" — acknowledge but suggest checkpoint workflow if complexity emerges

---

## 8. Integration with Other Skills

This skill works best alongside:
- **`resume-optimizer`** — Ensures all career materials are non-generic and production-grade
- **`proposal-pitch-deck-designer`** — Enforces checkpoint workflow for complex proposals
- **`ai-agent-development-deployment-architect`** — Uses orchestration protocols for agent management
- **`enterprise-sales-intelligence-architect`** — Applies negative constraints to competitive positioning

---

## 9. Quick Reference Card

| Protocol | When to Use | Key Action |
|----------|-----------|-----------|
| **Skill Sweet Spot** | You have 15+ skills active | Audit skills; merge or archive |
| **Negative Constraints** | Starting any design or code work | Apply design/code/doc constraints |
| **Checkpoint Workflow** | Complex task (>Step 4) | Plan → Mock → Execute → Verify → Document |
| **Session Hygiene** | ~30 messages or context shift | Suggest fresh start with handoff summary |
| **Artifact Standards** | Creating any deliverable | Use naming conventions, version, tag, store properly |

---

## Version History

- **v1.0.0** (2026-04-02): Initial release with 5 core protocols, trigger system, and integration guidelines
- Planned: v1.1 (Metrics dashboard for skill effectiveness)
- Planned: v1.2 (Auto-rotation trigger system)
