# Agent Orchestration Skill

> Protocols for managing the agentic environment, including skill evolution, checkpoint workflows, and negative constraint engineering.

A high-performance system prompt designed to maintain focus, prevent context bloat, and enforce quality standards in AI-assisted workflows. Perfect for consultants, founders, and teams managing complex multi-step projects with Claude.

---

## Features

✅ **Skill Sweet Spot Protocol** — Prevent context overload by maintaining 5-15 active skills  
✅ **Negative Constraint Engineering** — Enforce opinionated design and code standards  
✅ **Checkpoint Workflow** — Validate alignment before execution on complex tasks  
✅ **Session Hygiene** — Maintain reasoning clarity with rotation and persistence protocols  
✅ **Artifact Standards** — Professional naming, versioning, and storage conventions  

---

## Quick Start

### Option 1: Upload to Claude (Recommended)

1. **Copy the manifest:**
   ```json
   {
     "skill_id": "agent-orchestration",
     "name": "Agent Orchestration",
     "version": "1.0.0"
     // ... see manifest.json for full content
   }
   ```

2. **Upload via Claude.ai:**
   - Go to Settings → Skills (if available in your plan)
   - Upload `manifest.json` + `SKILL.md`
   - Set priority to "High"
   - Activate by default

3. **Usage:**
   - Skill auto-activates on relevant keywords
   - Mention "orchestration," "agent," or "checkpoint workflow" to trigger
   - Use `/agent-orchestration` to manually activate

### Option 2: Copy-Paste into System Prompt

If your Claude plan doesn't support skills:

1. Copy the contents of `SKILL.md`
2. Paste into your system prompt or custom instructions
3. Reference as needed

---

## Core Concepts

### 1. The Skill Sweet Spot Protocol

Prevent context bloat by maintaining 5-15 active skills at any time.

```
Active Skills: 7/15
- resume-optimizer
- proposal-pitch-deck-designer
- ai-agent-development-deployment-architect
- enterprise-sales-intelligence-architect
- contact-hunter
- executive-business-intelligence-synthesizer
- agent-orchestration (this one!)
```

**Pruning trigger:** If you exceed 15 skills, merge related ones or archive to `storage/`.

### 2. Negative Constraint Engineering

Avoid generic, "average" AI output by enforcing specific constraints:

| Category | Constraint | Rationale |
|----------|-----------|-----------|
| **Design** | No pure black/white, no Bootstrap look, no sharp corners | Opinionated, intentional aesthetics |
| **Code** | No snippets, no TODO placeholders, complete files | Production-ready on day one |
| **Docs** | Specific not generic, quantified impact, clear success metrics | Actionable and measurable |

### 3. Checkpoint Workflow

For complex tasks (>Step 4):

```
PLAN → MOCK → EXECUTE → VERIFY → DOCUMENT
```

Example:
```
PLAN: Describe approach in 5 bullets
MOCK: Show interface/schema before building
EXECUTE: Build after approval
VERIFY: Test against success criteria
DOCUMENT: Create implementation guide for reuse
```

### 4. Session Hygiene

Maintain reasoning sharpness:

- **Rotation trigger:** ~30 messages OR context shift
- **Persistence:** Check `.agent/notes.md` at session start
- **Handoff:** Write summary for next session

### 5. Artifact Standards

```
✓ File naming: snake_case or kebab-case
✓ Versioning: proposal-v2.1.pdf
✓ Dating: strategic-plan-2026-q2.md
✓ Tagging: [type: proposal] [client: Acme] [status: approved]
✓ Storage: artifacts/ or .agent/ folders, never chat-only
```

---

## When to Use This Skill

### Ideal Use Cases
- Managing 5+ concurrent projects
- Complex multi-step automations or proposals
- High-stakes client deliverables
- Building reusable frameworks or systems
- Maintaining consistency across team outputs

### Not Ideal For
- Simple one-off questions
- Minimal output tasks
- Casual brainstorming

---

## Integration with Other Skills

Works best alongside:

- **`resume-optimizer`** — Ensures career materials are non-generic
- **`proposal-pitch-deck-designer`** — Enforces checkpoint workflow
- **`ai-agent-development-deployment-architect`** — Manages agent workflows
- **`enterprise-sales-intelligence-architect`** — Applies constraints to competitive positioning

---

## Example: Checkpoint Workflow in Action

**Task:** Build a complex proposal with ROI calculator

**PLAN (Requested):**
```
1. Analyze client's current state and pain points
2. Design proposal structure with 3 solution tiers
3. Build ROI calculator with multiple scenarios
4. Create pitch deck with before/after comparisons
5. Package with implementation timeline and success metrics
```

**MOCK (Requested):**
```
[Show proposal outline, ROI calculator spreadsheet, deck structure]
Token estimate: 3,500 | Timeline: 2 hours | Approval: ✓
```

**EXECUTE:**
```
Building proposal-v1.0.docx, roi-calculator-v1.0.xlsx, pitch-deck-v1.0.pptx...
```

**VERIFY:**
```
✓ All files production-ready
✓ ROI scenarios validated
✓ Deck flows logically
✓ Success metrics clear
✓ Ready for client delivery
```

**DOCUMENT:**
```
→ Saved to artifacts/
→ Created IMPLEMENTATION_GUIDE.md
→ Logged to .agent/notes.md for reuse
```

---

## Configuration

### Environment Variables (Optional)

```bash
# .agent/config.env
MAX_SKILLS=15
MIN_SKILLS=5
CHECKPOINT_THRESHOLD=4  # Trigger checkpoint for steps > 4
SESSION_ROTATION_MESSAGES=30
ARTIFACT_STORAGE_PATH=./artifacts/
```

### Customization

You can override the skill's behavior:

- **"NO CONSTRAINTS"** — Temporarily disable negative constraint engineering
- **"DRAFT MODE"** — Relax production-ready requirements
- **"SIMPLE"** — Acknowledge but suggest checkpoint workflow if complexity emerges

---

## Best Practices

1. **Review skill count monthly** — Prune if exceeding 15 skills
2. **Use checkpoint workflow for high-stakes work** — Don't skip the PLAN → MOCK steps
3. **Store artifacts properly** — Never rely on chat history as source of truth
4. **Rotate sessions** — Start fresh after ~30 messages for clarity
5. **Tag all deliverables** — Use metadata for searchability

---

## Metrics & Effectiveness

| Metric | Benchmark | Your Target |
|--------|-----------|-----------|
| Avg. tokens per artifact | 2,000-3,000 | Optimize for clarity over verbosity |
| Production-ready output % | 80%+ | Aim for 90%+ |
| Session length before rotation | 30 messages | Adjust based on context quality |
| Skills active per session | 5-15 | Audit quarterly |

---

## Support & Contribution

**Issues or suggestions?**
- Open an issue on GitHub
- Email: bockrath.ai@gmail.com
- Reference: MAB AI Strategies LLC

**Want to extend this skill?**
- Submit a pull request with your protocol additions
- Ensure changes maintain the "opinionated, high-performance" philosophy
- Update version number and CHANGELOG

---

## License

MIT License — See `LICENSE` file for details.

---

## Changelog

### v1.0.0 (2026-04-02)
- Initial release
- 5 core protocols: Skill Sweet Spot, Negative Constraints, Checkpoint Workflow, Session Hygiene, Artifact Standards
- Integration guidelines with related skills
- Quick reference card and examples

### Planned
- v1.1: Metrics dashboard for skill effectiveness
- v1.2: Auto-rotation trigger system with transcript analysis
- v1.3: Multi-agent orchestration protocols

---

**Built by Mark Bockrath | MAB AI Strategies LLC**  
*High-performance AI orchestration for consultants, founders, and teams.*
