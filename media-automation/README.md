# Media Production & Posting Automation

See main [TOOL-RESEARCH.md](../TOOL-RESEARCH.md) for detailed tool analysis.

## Quick Start

### Recommended Stack
1. **Typefully** — Twitter scheduling
2. **Claude** — Content generation
3. **OpenRouter** — Cheap triage/classification
4. **X API Basic** ($100/mo) — Monitoring

### Implementation Plan

#### Phase 1: Setup (Week 1)
- [ ] Create Typefully account
- [ ] Connect X API
- [ ] Set up OpenRouter
- [ ] Build content templates
- [ ] Create 14 posts

#### Phase 2: Automation (Week 2)
- [ ] Git webhook → post generator
- [ ] Research agent for trending topics
- [ ] Draft generator
- [ ] Scheduling system

#### Phase 3: Optimization (Ongoing)
- [ ] Analytics tracking
- [ ] A/B testing hooks
- [ ] Content mix adjustment
- [ ] Thread creation

---

## Content Templates

### Template 1: Build in Public
```
Shipped [feature/project] today.

What it does: [1 sentence]
Tech stack: [technologies]
Time invested: [duration]
Lesson learned: [insight]

[screenshot/demo]

What's next? [next step]
```

### Template 2: Tech Insight
```
Hot take: [controversial statement]

Here's why:
1. [point]
2. [point]
3. [point]

Counter-argument: [address it]

What's your experience?
```

### Template 3: Client Lesson (Anonymized)
```
A client came to me with [problem].

Their situation: [context]
What we tried: [approach]
What worked: [solution]
Result: [outcome]

The lesson: [insight]

Have you faced this?
```

---

## Automation Scripts

See `templates/` folder for:
- `git-to-post.py` — Convert commits to posts
- `research-agent.py` — Scan for trending topics
- `draft-generator.py` — Generate post drafts
- `scheduler.py` — Queue content

---

*Detailed implementation delegated to FORGEs after questionnaire completion.*
