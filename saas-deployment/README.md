# SaaS Rapid Deployment

See main [TOOL-RESEARCH.md](../TOOL-RESEARCH.md) for detailed tool analysis.

## Quick Start

### Recommended Stack
1. **Railway** — Hosting (consistent with Eyedentity)
2. **PostgreSQL** — Database
3. **Mastra + Vercel AI SDK** — AI features
4. **Stripe** — Payments
5. **Resend** — Email
6. **AWS Cognito or Clerk** — Auth

### Product Selection Framework

#### Criteria
- Buildable in 2-4 weeks
- Clear value proposition
- Monetizable ($10-50/mo)
- Differentiated
- You'd use it

#### Candidates from Eyedentity Roadmap
Review `Personal-Brand/Portfolio/Apps/APPS-ROADMAP.md` for candidates.

#### Alternative: Scratch Your Own Itch
What problem do you have that you'd pay to solve?

---

## Implementation Plan

### Week 1: Planning
- [ ] Product selection
- [ ] Technical design
- [ ] UI mockups (Figma or sketch)
- [ ] Database schema
- [ ] Repo setup + CI/CD

### Week 2-3: Core Development
- [ ] Auth implementation
- [ ] Database + API
- [ ] Core features
- [ ] Basic UI

### Week 4: Polish & Launch
- [ ] Payment integration
- [ ] Landing page
- [ ] Documentation
- [ ] Beta testing
- [ ] Product Hunt prep

---

## Templates

See `templates/` folder for:
- `saas-starter/` — Next.js + Mastra + Stripe boilerplate
- `landing-page/` — High-converting SaaS landing
- `pricing-page/` — Pricing tier component
- `auth-flow/` — Cognito/Clerk integration

---

*Detailed implementation delegated to FORGEs after questionnaire completion.*
