# Agent Orchestration Skill — Implementation Guide

This guide walks you through adopting the Agent Orchestration skill across your workflows, teams, and AI platforms.

---

## Table of Contents

1. [Individual Adoption](#individual-adoption)
2. [Team Adoption](#team-adoption)
3. [Platform Integration](#platform-integration)
4. [Measurement & Optimization](#measurement--optimization)
5. [Troubleshooting](#troubleshooting)

---

## Individual Adoption

### Phase 1: Foundation (Week 1)

**Goal:** Understand and test all 5 protocols in isolation.

#### Step 1.1: Read & Internalize
- [ ] Read `SKILL.md` fully
- [ ] Highlight the 5 core protocols
- [ ] Note which protocols apply to your current work

#### Step 1.2: Audit Current State
- Count active skills/tools you're using
- Document typical session length (# of messages)
- Note 3 artifacts you've created recently
- Review for generic patterns (Bootstrap UI, TODO comments, vague deliverables)

#### Step 1.3: Apply One Protocol
**Start with:** Negative Constraint Engineering (easiest to implement immediately)

Action:
- On your next design/code task, explicitly ban: pure black/white, generic UI, unfinished code
- Review output — note quality difference
- Document observations

### Phase 2: Integration (Week 2-3)

#### Step 2.1: Adopt Artifact Standards
- Create `.agent/` folder in your workspace
- Move 3 recent deliverables there with proper naming:
  - `proposal-v1.0.docx`
  - `automation-framework-v1.2.json`
  - `roi-calculator-v2.1.xlsx`
- Tag each with metadata (type, client, status)

#### Step 2.2: Try Checkpoint Workflow
On your next complex task:
- Use the PLAN → MOCK → EXECUTE → VERIFY → DOCUMENT sequence
- Time each phase
- Compare to your typical approach

#### Step 2.3: Implement Session Hygiene
- Create `.agent/active_task.md` template:
  ```markdown
  # Active Task
  **Start:** 2026-04-02 | **Status:** In Progress
  
  ## Current Work
  - [x] Phase 1
  - [ ] Phase 2
  
  ## Progress
  [Notes here]
  
  ## Next Steps
  1. Action
  2. Action
  
  ## Key Decisions
  - Decision 1: Rationale
  ```
- Use this for your next project

### Phase 3: Mastery (Week 4+)

#### Step 3.1: Audit Skill Count
- List all active skills/tools
- Merge related ones if >15
- Create `skills/archived/` for less-used tools
- Maintain 5-15 active at all times

#### Step 3.2: Optimize for Your Role
Customize the protocols based on your needs:

**For Consultants:**
- Emphasize Checkpoint Workflow for client projects
- Use Artifact Standards for deliverable consistency
- Track ROI improvements with Negative Constraints

**For Builders/Engineers:**
- Emphasize Negative Constraints for code quality
- Use Skill Sweet Spot for tool management
- Document learnings in Artifact Standards

**For Founders:**
- Emphasize Session Hygiene for context clarity
- Use Checkpoint Workflow for strategic decisions
- Track metrics for all major projects

#### Step 3.3: Measure Impact
Create a simple tracker:

```markdown
# Agent Orchestration Metrics

## Negative Constraints
| Metric | Before | After | Change |
|--------|--------|-------|--------|
| Production-ready % | 60% | 85% | +25% |
| Time to polish | 45 min | 15 min | -67% |

## Checkpoint Workflow
| Metric | Before | After | Change |
|--------|--------|-------|--------|
| Rework cycles | 2.3 avg | 1.1 avg | -52% |
| Stakeholder approval time | 3 days | 1 day | -67% |

## Session Hygiene
| Metric | Before | After | Change |
|--------|--------|-------|--------|
| Avg session length (messages) | 45 | 28 | -38% |
| Context clarity | 6/10 | 9/10 | +50% |
```

---

## Team Adoption

### For Consultancies & Agencies

#### Phase 1: Centralized Rollout (Week 1-2)

1. **Orient the team:**
   - Share `README.md` with all staff
   - 30-min team meeting: Walk through the 5 protocols
   - Answer: "How does this improve our client work?"

2. **Create shared standards:**
   - `.agent/` folder structure in shared drive
   - Naming convention guide (use in all proposals/deliverables)
   - Artifact tagging standard: `[type] [client] [status] [version]`

3. **Assign champions:**
   - 1-2 people per protocol (to coach others)
   - Weekly 15-min sync to troubleshoot

#### Phase 2: Integration (Week 3-4)

- **All proposals** use Checkpoint Workflow
- **All code** follows Negative Code Constraints
- **All deliverables** stored in centralized artifacts folder with metadata
- **Weekly audit:** Skill count, artifact quality, session lengths

#### Phase 3: Optimization (Month 2+)

- Track ROI improvements by skill
- Create internal case studies
- Build skill library (merge/archive unused tools)
- Celebrate wins: "This quarter: 40% faster proposal delivery"

### For Product Teams

#### Adapt the Protocols

**Skill Sweet Spot → Tool Ecosystem**
- Limit tech stack to 5-15 core tools
- Archive or deprecate overlapping solutions
- Monthly tool review meeting

**Checkpoint Workflow → Product Sprints**
- PLAN: Requirements gathering
- MOCK: Wireframes/prototypes
- EXECUTE: Development
- VERIFY: QA/testing
- DOCUMENT: Release notes & runbooks

**Negative Constraints → Design System**
- Define opinionated design rules
- Ban generic components (Material UI only if extended)
- Require design review before dev
- Code review gates for standards compliance

---

## Platform Integration

### Claude.ai / Claude API

#### Option 1: Skill Upload (Recommended)

1. Go to **Settings → Skills** (Pro/Team plan required)
2. Click **"Add Skill"**
3. Upload `manifest.json` + `SKILL.md`
4. Set priority: **High**
5. Enable: **Active by default**
6. Save

Once uploaded:
- Skill activates automatically on trigger keywords
- Use `/agent-orchestration` to manually invoke
- Appears in context window when active

#### Option 2: Custom Instructions (Free alternative)

1. Go to **Settings → Custom Instructions**
2. Copy-paste `SKILL.md` content into **System Prompt** field
3. Save
4. Skill is now active for all conversations

### Other AI Platforms (OpenAI, Anthropic API, etc.)

#### For OpenAI (ChatGPT, o1, etc.)

Add to system prompt:
```
[Agent Orchestration Skill v1.0 Active]

You are using the Agent Orchestration skill. Adhere to these protocols:
1. Skill Sweet Spot: Maintain 5-15 active capabilities
2. Negative Constraints: Enforce design/code quality standards
3. Checkpoint Workflow: Use PLAN→MOCK→EXECUTE→VERIFY→DOCUMENT
4. Session Hygiene: Suggest rotation after 30 messages
5. Artifact Standards: Professional naming, versioning, storage

[See full skill definition at: ...]
```

#### For Anthropic API

Include in system prompt parameter:

```python
import anthropic

client = anthropic.Anthropic()

system_prompt = """
[Agent Orchestration Skill v1.0]

[Full SKILL.md content here]

Adhere to these protocols in all responses...
"""

message = client.messages.create(
    model="claude-opus-4-20250514",
    max_tokens=2048,
    system=system_prompt,
    messages=[
        {"role": "user", "content": "Your prompt here"}
    ]
)
```

#### For Local LLMs (Ollama, LLaMA, Mistral)

Add to `system.txt` or context prompt:

```
Agent Orchestration Protocol Version 1.0

This AI assistant follows strict protocols for:
- Skill management (maintain 5-15 active tools)
- Quality constraints (no generic design/code)
- Checkpoint workflows (PLAN → MOCK → EXECUTE → VERIFY → DOCUMENT)
- Session management (rotate after 30 messages)
- Artifact standards (versioning, naming, storage)

[Full protocols below...]
```

---

## Measurement & Optimization

### Define Success Metrics

Choose 3-5 metrics relevant to your role:

**For Consultants:**
```
1. Proposal approval time (target: 1 day vs 3 days)
2. Client revision cycles (target: 1.1 vs 2.3)
3. Production-ready deliverables % (target: 90% vs 60%)
4. Artifact reuse rate (track which templates get copied)
5. Time to next similar project (target: 50% faster)
```

**For Builders:**
```
1. Code quality (bugs per 1000 LOC: target 2 vs 8)
2. Time to production (target: reduce by 30%)
3. Technical debt incidents (target: reduce by 40%)
4. Documentation completeness % (target: 95% vs 60%)
5. Codebase clarity (peer review satisfaction: target 8/10)
```

**For Founders:**
```
1. Strategic decision clarity (1-10 scale: target 8 vs 5)
2. Session context quality (1-10 scale: target 9 vs 6)
3. Artifact library size (target: 50+ reusable templates)
4. Time from idea to execution (target: 30% faster)
5. Stakeholder alignment (approval cycles: target 1 vs 2)
```

### Monthly Review

Create a dashboard:

```markdown
# Agent Orchestration Metrics Dashboard — April 2026

## Adoption Status
- Skill count: 12/15 (optimal)
- Session avg length: 28 messages (target: <30) ✓
- Checkpoint workflow usage: 85% of complex tasks ✓

## Quality Improvements
- Production-ready %: 87% (target: 90%)
- Negative constraints applied: 78% of code/design work
- Artifact reuse rate: 6 templates used 3+ times

## Business Impact
- Proposal delivery time: 18 hours (was 24) = +33% faster
- Revision cycles: 1.2 (was 2.1) = -43% rework
- Client satisfaction (quality): 8.9/10 (was 7.2)

## Next Month Actions
- [ ] Optimize 3 low-performing templates
- [ ] Audit & merge 2 redundant skills
- [ ] Implement metrics automation
```

### Quarterly Optimization

Every 3 months:

1. **Audit protocols:**
   - Which 2 protocols delivered most value?
   - Which protocol needs improvement?
   - Suggest customizations

2. **Prune skill library:**
   - Remove unused skills
   - Merge overlapping capabilities
   - Document "archive" decisions

3. **Share learnings:**
   - Case study: "How Agent Orchestration reduced proposal time by 40%"
   - Updated best practices guide
   - Celebrate team wins

---

## Troubleshooting

### Problem: "The constraints feel restrictive"

**Solution:**
- Constraints are guidelines, not hard rules
- Use override triggers: "NO CONSTRAINTS," "DRAFT MODE," "SIMPLE"
- Customize constraints for your context (see `SKILL.md` section 2)
- Remember: Constraints prevent generic output, not creativity

### Problem: "I keep forgetting to use the protocols"

**Solution:**
- Add `.agent/active_task.md` to every new project
- Pin the quick reference card (section 9 of SKILL.md)
- Set calendar reminder: "Weekly skill audit"
- Ask Claude: "Which protocol should I use here?"

### Problem: "Checkpoint workflow feels slow"

**Solution:**
- Skip for simple tasks (<Step 4)
- Combine PLAN + MOCK in one prompt to save time
- Use template prompts (see examples in docs/)
- Track: Time spent in planning vs. rework — usually net saves time

### Problem: "Our team isn't adopting this"

**Solution:**
- **Quick win:** Start with Negative Constraints only (easiest to see value)
- **Show ROI:** Demonstrate metrics from phase 1 (e.g., "40% less rework")
- **Make it mandatory:** Include in project checklists
- **Celebrate wins:** "Sarah used Checkpoint Workflow → client approved in 1 call"

### Problem: "Session rotation is breaking my workflow"

**Solution:**
- Rotate only when quality degrades (not strictly at 30 messages)
- Use `.agent/notes.md` to preserve context perfectly
- Extend if you're in deep flow (ignore hard limit)
- Test: Does new session actually improve clarity?

---

## Next Steps

1. **Pick your role:** Consultant / Builder / Founder
2. **Start Phase 1:** Read + Audit + Apply One Protocol
3. **Track progress:** Use the metrics template
4. **Review monthly:** Adjust based on what's working
5. **Share learnings:** Help your team/network adopt

---

**Questions?** Email: bockrath.ai@gmail.com  
**Want to contribute?** Submit pull requests to the GitHub repo  
**Found a bug?** Open an issue with details and screenshots

---

*Last Updated: 2026-04-02*  
*Version: 1.0.0*  
*By: Mark Bockrath, MAB AI Strategies LLC*
