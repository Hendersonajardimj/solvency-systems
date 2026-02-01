# Tool Research: Solvency Systems

**Last Updated:** 2026-02-01  
**Purpose:** Comprehensive tool analysis for all three solvency tracks

---

## Table of Contents
1. [Media Production & Posting Automation](#1-media-production--posting-automation)
2. [SaaS Rapid Deployment](#2-saas-rapid-deployment)
3. [Portfolio Site Development](#3-portfolio-site-development)
4. [Upwork Automation](#4-upwork-automation)
5. [Cross-Cutting Tools](#5-cross-cutting-tools)
6. [Cost Analysis](#6-cost-analysis)
7. [Recommendations](#7-recommendations)

---

## 1. Media Production & Posting Automation

### 1.1 Content Schedulers

#### Typefully (Recommended for Twitter-first)
**Website:** https://typefully.com  
**Pricing:** Free tier (100 tweets/month), $12.50/mo Pro, $29/mo Teams

**Pros:**
- Purpose-built for Twitter/X threads
- Best-in-class thread writing UX
- Analytics and engagement tracking
- Auto-retweet and auto-plug features
- Queue and scheduling
- Free tier sufficient for testing

**Cons:**
- Twitter/X only (no LinkedIn, etc.)
- Limited API access
- No AI content generation built-in

**Best For:** Twitter-first strategy, thread-heavy content

**Integration:** Manual export/import or use their API (limited)

---

#### Buffer
**Website:** https://buffer.com  
**Pricing:** Free (3 channels), $6/mo/channel Essentials, $12/mo/channel Team

**Pros:**
- Multi-platform (Twitter, LinkedIn, Facebook, Instagram, Pinterest)
- Established, reliable
- Good analytics
- Browser extension
- Mobile app
- Affordable for small scale

**Cons:**
- Thread support limited (manual threading)
- Less Twitter-native than Typefully
- Can get expensive with many channels

**Best For:** Multi-platform presence, established workflow

**Integration:** Good API for automation

---

#### Hypefury
**Website:** https://hypefury.com  
**Pricing:** $19/mo Standard, $49/mo Premium

**Pros:**
- Twitter-focused growth features
- Auto-retweet best posts
- Auto-plug (promote newsletter/offer)
- Evergreen content recycling
- Engagement features

**Cons:**
- More expensive
- Can feel spammy if overused
- Learning curve

**Best For:** Growth-focused Twitter strategy

---

#### Custom Build
**Stack:** Next.js + BullMQ + X API

**Pros:**
- Full control
- Custom AI integration
- Cost scales with usage
- No vendor lock-in

**Cons:**
- Significant dev time
- X API costs ($100/mo basic, $5000/mo premium)
- Maintenance burden
- Rate limits to manage

**Best For:** Long-term, scale, specific requirements

---

### 1.2 AI Content Generation

#### Claude (Anthropic)
**Models:** Haiku (fast/cheap), Sonnet (balanced), Opus (powerful)
**Pricing:** Haiku $0.25/1M tokens, Sonnet $3/1M tokens

**Pros:**
- Best for long-form, nuanced content
- Excellent for thread structuring
- Great at maintaining voice
- JSON mode for structured output

**Cons:**
- More expensive than some alternatives
- Rate limits on lower tiers

**Best For:** High-quality content, thread drafting

---

#### OpenRouter
**Website:** https://openrouter.ai  
**Models:** Access to 100+ models via single API

**Pros:**
- Route to cheapest model for task
- Fallback models
- Pay-as-you-go
- No rate limits
- Good for triage/classification

**Cons:**
- Slightly higher latency
- Variable quality by model

**Best For:** Cost optimization, fallback strategies

**Recommended Models:**
- Triage/classification: Mistral 7B (~$0.10/1M tokens)
- Draft generation: Claude Haiku or GPT-3.5
- Final polish: Claude Sonnet

---

#### Groq
**Website:** https://groq.com  
**Models:** Llama 3, Mixtral

**Pros:**
- Extremely fast inference
- Very cheap
- Good for real-time applications

**Cons:**
- Limited model selection
- Newer (less mature)

**Best For:** High-volume, low-latency tasks

---

### 1.3 Research & Monitoring

#### X API (Twitter)
**Pricing:** 
- Free: 100 reads/month (insufficient)
- Basic: $100/month, 10,000 reads/month
- Pro: $5000/month

**Pros:**
- Direct access
- Real-time streaming possible
- No third-party limits

**Cons:**
- Expensive
- Complex rate limits
- Aggressive restrictions

**Verdict:** Use Basic tier ($100/mo) if X is primary platform

---

#### Nitter (Unofficial)
**Status:** Community instances, unreliable

**Pros:**
- Free
- No rate limits

**Cons:**
- Unreliable (instances get blocked)
- No official support
- Ethically gray

**Verdict:** Not recommended for production

---

#### RSS + Web Scraping (Hacker News, Blogs)
**Tools:** 
- RSS feeds (free)
- Scraping: ScrapingBee, ScrapingAnt, or custom

**Pros:**
- Free or cheap
- No API limits
- Good for research

**Cons:**
- Delayed vs. real-time
- Requires maintenance

---

### 1.4 Analytics

#### Twitter Analytics (Native)
**Pros:** Free, built-in
**Cons:** Limited export, no cross-platform

---

#### Typefully Analytics
**Pros:** Great thread analytics, engagement timing
**Cons:** Twitter only

---

#### Custom Dashboard
**Stack:** Metabase (open source), PostgreSQL, cron jobs

**Pros:**
- Full control
- Custom metrics
- Free (self-hosted)

**Cons:**
- Setup required
- Maintenance

---

## 2. SaaS Rapid Deployment

### 2.1 Hosting Platforms

#### Railway (Recommended for Eyedentity alignment)
**Website:** https://railway.app  
**Pricing:** $5/mo starter, usage-based

**Pros:**
- Simplest deployment
- PostgreSQL + Redis included
- Good for AI coding agents
- Fast iteration
- Matches Eyedentity stack

**Cons:**
- Can get expensive at scale
- Less control than AWS

**Best For:** MVP, rapid iteration, matching Eyedentity

---

#### Vercel
**Website:** https://vercel.com  
**Pricing:** Free tier, $20/mo Pro

**Pros:**
- Best Next.js hosting
- Edge functions
- Preview deployments
- Generous free tier

**Cons:**
- Stateless only (no background jobs easily)
- Database separate

**Best For:** Frontend-heavy SaaS, JAMstack apps

---

#### Render
**Website:** https://render.com  
**Pricing:** Free tier, $7/mo standard

**Pros:**
- Simple like Railway
- Background workers
- Cron jobs
- Good free tier

**Cons:**
- Slower than Vercel for frontends
- Less ecosystem

---

#### AWS (SST)
**Website:** https://sst.dev  
**Pricing:** Pay for what you use

**Pros:**
- Full AWS power
- Cost-effective at scale
- Enterprise-ready

**Cons:**
- Complex
- Slower iteration
- Overkill for MVP

**Best For:** Scale phase, not MVP

---

### 2.2 Database Options

#### PostgreSQL (Railway)
**Pricing:** Included in Railway

**Pros:**
- Full featured
- Prisma support
- JSON fields for flexibility
- Reliable

**Cons:**
- Overkill for simple apps

---

#### Supabase
**Website:** https://supabase.com  
**Pricing:** Free tier, $25/mo Pro

**Pros:**
- PostgreSQL + auth + storage
- Real-time subscriptions
- Generous free tier
- Good DX

**Cons:**
- Another platform to manage

**Best For:** Rapid prototyping, auth included

---

#### SQLite (Turso)
**Website:** https://turso.tech  
**Pricing:** Free tier (9GB), $29/mo Pro

**Pros:**
- Extremely cheap
- Edge distributed
- Good for simple SaaS

**Cons:**
- Limited feature set
- Different from Eyedentity stack

---

### 2.3 AI Integration

#### Mastra (Eyedentity choice)
**Website:** https://mastra.ai  
**Status:** Open source, emerging

**Pros:**
- TypeScript-native
- Agent orchestration
- Works with Vercel AI SDK
- Matches Eyedentity stack

**Cons:**
- Newer, less mature
- Smaller community

---

#### Vercel AI SDK
**Website:** https://sdk.vercel.ai  
**Pricing:** Free, usage-based for some features

**Pros:**
- Streaming support
- Multiple providers
- React hooks
- Industry standard

**Cons:**
- You bring your own backend

---

#### LangChain
**Website:** https://langchain.com  
**Pricing:** Open source, LangSmith paid

**Pros:**
- Mature ecosystem
- Lots of integrations
- Agents, chains, tools

**Cons:**
- Can be overkill
- Abstractions sometimes leaky

---

### 2.4 Payment Processing

#### Stripe
**Website:** https://stripe.com  
**Pricing:** 2.9% + 30¢ per transaction

**Pros:**
- Industry standard
- Excellent developer experience
- Subscriptions, invoicing
- Tax handling (TaxJar integration)

**Cons:**
- Requires business entity for some features

**Verdict:** Default choice for SaaS

---

#### Lemon Squeezy
**Website:** https://lemonsqueezy.com  
**Pricing:** 5% + 50¢ per transaction

**Pros:**
- Merchant of record (handles tax)
- Great for solo founders
- Simple setup

**Cons:**
- More expensive
- Less mature

**Best For:** International, tax complexity avoidance

---

### 2.5 Email & Communication

#### Resend
**Website:** https://resend.com  
**Pricing:** Free (3000/month), $20/mo (50k)

**Pros:**
- Built for developers
- Great deliverability
- Simple API

**Cons:**
- No marketing automation

---

#### Loops
**Website:** https://loops.so  
**Pricing:** Free (1000 contacts), $39/mo (10k)

**Pros:**
- SaaS-focused email
- Automation workflows
- Product updates, newsletters

**Cons:**
- Newer product

---

#### Postmark
**Website:** https://postmarkapp.com  
**Pricing:** $15/mo (10k emails)

**Pros:**
- Transactional focus
- Excellent deliverability
- Reliable

---

### 2.6 Authentication

#### AWS Cognito (Eyedentity choice)
**Pricing:** 50,000 MAU free, then tiered

**Pros:**
- Scales infinitely
- Enterprise-ready
- Free tier generous

**Cons:**
- Complex setup
- AWS ecosystem lock-in

---

#### Clerk
**Website:** https://clerk.com  
**Pricing:** Free (10k MAU), $25/mo Pro

**Pros:**
- Best developer experience
- Pre-built UI components
- Organizations support

**Cons:**
- Another vendor
- Costs at scale

**Best For:** Speed, great UX

---

#### Supabase Auth
**Pricing:** Included

**Pros:**
- Included with database
- Simple
- Good for MVPs

**Cons:**
- Less flexible than Cognito/Clerk

---

## 3. Portfolio Site Development

### 3.1 Static Site Generators

#### Next.js (Recommended for consistency)
**Pros:**
- Matches Eyedentity stack
- Full React power
- SSG/SSR flexibility
- Image optimization
- Easy to extend

**Cons:**
- More complex than pure static

---

#### Astro
**Website:** https://astro.build  
**Pricing:** Free

**Pros:**
- Fast, minimal JS
- Great for content sites
- Islands architecture
- Good DX

**Cons:**
- Different stack from Eyedentity

**Best For:** Content-heavy portfolios

---

#### 11ty
**Website:** https://11ty.dev  
**Pricing:** Free

**Pros:**
- Simple
- Fast
- Flexible templating

**Cons:**
- Less ecosystem

---

### 3.2 No-Code/Low-Code Options

#### Framer
**Website:** https://framer.com  
**Pricing:** Free (framer.site domain), $15/mo mini, $25/mo basic

**Pros:**
- Designer-quality sites
- Fast
- CMS included
- Great animations

**Cons:**
- Locked into Framer
- Less flexible

**Best For:** Design-focused portfolios, speed

---

#### Webflow
**Website:** https://webflow.com  
**Pricing:** $14/mo basic, $23/mo CMS

**Pros:**
- Powerful
- CMS
- Designer-friendly
- Good SEO

**Cons:**
- Learning curve
- Export limited

---

#### Carrd
**Website:** https://carrd.co  
**Pricing:** Free, $19/year Pro

**Pros:**
- Extremely cheap
- Simple
- Good for single-page

**Cons:**
- Limited
- Not professional enough for some use cases

---

### 3.3 CMS Options

#### MDX (Local)
**Pros:**
- Version controlled
- Free
- Fast

**Cons:**
- Requires code changes for updates

---

#### Sanity
**Website:** https://sanity.io  
**Pricing:** Free tier, $99/mo team

**Pros:**
- Structured content
- Great developer experience
- GROQ query language

---

#### Notion (as CMS)
**Tools:** Notion + Super.so or Potion

**Pros:**
- Write in Notion
- Easy updates

**Cons:**
- Dependent on Notion
- Slower

---

## 4. Upwork Automation

### 4.1 Job Scanning

#### Upwork RSS Feeds
**Pros:**
- Free
- Real-time

**Cons:**
- Limited filtering
- Basic info only

---

#### Upwork API
**Pricing:** Enterprise only ($$$)

**Verdict:** Not accessible for freelancers

---

#### Scraping Solutions

**ScrapingBee**
**Website:** https://scrapingbee.com  
**Pricing:** $49/mo starter

**Pros:**
- Reliable proxy rotation
- JavaScript rendering
- Good support

---

**ScrapingAnt**
**Website:** https://scrapingant.com  
**Pricing:** $19/mo starter

**Pros:**
- Cheaper
- Good for simple scraping

---

**Playwright + Proxies (Custom)**
**Cost:** ~$20-50/mo for proxies

**Pros:**
- Full control
- No third-party limits

**Cons:**
- Maintenance
- Cat-and-mouse with anti-bot

---

### 4.2 Proposal Generation

#### Claude (Recommended)
- Generate proposals from job descriptions
- Customize based on your portfolio
- Maintain consistent voice

---

#### Custom Templates + Variables
- Pre-written templates
- Variable substitution
- Manual customization

---

### 4.3 Upwork Management Tools

**No good third-party tools exist** due to Upwork's ToS restrictions.

**Recommended approach:**
- Browser extension (custom) for job alerts
- Templated responses
- CRM (Airtable/Notion) for tracking

---

## 5. Cross-Cutting Tools

### 5.1 Task & Project Management

#### Notion
**Pricing:** Free personal, $8/mo team

**Pros:**
- Flexible
- Database views
- Good for solo operators

---

#### Linear
**Website:** https://linear.app  
**Pricing:** Free, $8/mo

**Pros:**
- Fast
- Keyboard-driven
- Great for development

---

#### GitHub Projects
**Pricing:** Free

**Pros:**
- Integrated with code
- Simple

---

### 5.2 Documentation

#### Notion
- Flexible
- Good for wikis

---

#### Outline
**Website:** https://outline.com  
**Pricing:** Self-hosted or paid

**Pros:**
- Wiki-focused
- Fast
- Open source option

---

#### GitBook
**Website:** https://gitbook.com  
**Pricing:** Free (open source), $6.70/mo

**Pros:**
- Great documentation UX
- Syncs with GitHub

---

### 5.3 Analytics

#### Plausible
**Website:** https://plausible.io  
**Pricing:** $9/mo (10k pageviews)

**Pros:**
- Privacy-focused
- Lightweight
- No cookie banner needed

---

#### Google Analytics 4
**Pricing:** Free

**Pros:**
- Free
- Comprehensive

**Cons:**
- Privacy concerns
- Complex
- Cookie banner required

---

#### PostHog
**Website:** https://posthog.com  
**Pricing:** Free (1M events/mo)

**Pros:**
- Open source
- Product analytics
- Session recording
- Feature flags

---

### 5.4 Error Tracking

#### Sentry
**Website:** https://sentry.io  
**Pricing:** Free (5k errors/mo), $26/mo

**Pros:**
- Industry standard
- Great for debugging

---

#### LogRocket
**Website:** https://logrocket.com  
**Pricing:** Free (1k sessions/mo)

**Pros:**
- Session replay
- Great for UX debugging

---

### 5.5 Cron & Job Scheduling

#### GitHub Actions
**Pricing:** Free (2000 min/mo)

**Pros:**
- Free
- Integrated with repos

**Cons:**
- Limited scheduling
- Overkill for simple jobs

---

#### Railway Cron
**Pricing:** Included with Railway

**Pros:**
- Simple
- Integrated with deployment

---

#### Temporal
**Website:** https://temporal.io  
**Pricing:** Cloud or self-hosted

**Pros:**
- Durable execution
- Complex workflows

**Cons:**
- Overkill for simple cron

---

## 6. Cost Analysis

### 6.1 Minimum Viable Stack (Monthly)

| Tool | Cost | Purpose |
|------|------|---------|
| Railway | $5 | Hosting |
| PostgreSQL | $0 (included) | Database |
| Resend | $0 (free tier) | Email |
| Plausible | $9 | Analytics |
| X API Basic | $100 | Social monitoring |
| Typefully | $0 (free) | Scheduling |
| Claude API | ~$20 | AI content |
| OpenRouter | ~$10 | Cheap AI tasks |
| **Total** | **~$144/mo** | |

---

### 6.2 Comfortable Stack (Monthly)

| Tool | Cost | Purpose |
|------|------|---------|
| Railway | $20 | Better hosting |
| Supabase | $25 | Database + auth |
| Resend | $20 | More email |
| Plausible | $9 | Analytics |
| X API Basic | $100 | Social monitoring |
| Typefully Pro | $12.50 | Better scheduling |
| Buffer | $18 | Multi-platform |
| Claude API | $50 | AI content |
| OpenRouter | $20 | Cheap AI tasks |
| Sentry | $26 | Error tracking |
| **Total** | **~$300/mo** | |

---

### 6.3 At Scale (Monthly)

| Tool | Cost | Purpose |
|------|------|---------|
| AWS (SST) | $200+ | Scale hosting |
| Stripe | ~3% | Payments |
| Multiple APIs | $300+ | Various |
| **Total** | **$500-1000+/mo** | |

---

## 7. Recommendations

### 7.1 Media Production (Track 1)

**Start with:**
1. **Typefully** for Twitter scheduling (free tier)
2. **Claude** for content generation
3. **OpenRouter** (Mistral 7B) for triage/classification
4. **X API Basic** ($100/mo) for monitoring

**Upgrade path:**
- Typefully Pro when exceeding free tier
- Add Buffer if expanding to LinkedIn
- Consider custom scheduler at 10k+ followers

---

### 7.2 SaaS Deployment (Track 2)

**For rapid deployment:**
1. **Railway** for hosting (consistent with Eyedentity)
2. **PostgreSQL** via Railway
3. **Mastra + Vercel AI SDK** for AI features
4. **Stripe** for payments
5. **Resend** for transactional email
6. **AWS Cognito** for auth (or Clerk for speed)

**For speed (alternative):**
1. **Supabase** (db + auth + storage)
2. **Vercel** for frontend
3. **Stripe** for payments

---

### 7.3 Portfolio Site (Track 3)

**Fastest:**
- **Framer** ($15/mo) — live in 1-2 days

**Best long-term:**
- **Next.js** on **Vercel** — matches Eyedentity, extensible

**Middle ground:**
- **Astro** on **Vercel** — faster than Next.js, still flexible

---

### 7.4 Upwork Automation (Track 3)

**Current reality:** Upwork heavily restricts automation

**Workable approach:**
1. **RSS feeds** for job alerts
2. **Browser extension** (custom) for quick apply
3. **Claude** for proposal drafting
4. **Notion/Airtable** for CRM tracking

**Avoid:** Full automation (risk of account ban)

---

### 7.5 Integrated Stack Summary

**Phase 1 (Weeks 1-4):**
- Railway ($5)
- Typefully (free)
- Claude + OpenRouter (~$30)
- X API ($100)
- Framer portfolio ($15) OR Next.js
- **Total: ~$150/mo**

**Phase 2 (Weeks 5-12):**
- Add SaaS product on Railway
- Stripe integration
- Resend email
- **Total: ~$200-300/mo**

**Phase 3 (Scale):**
- Migrate to AWS if needed
- Full marketing stack
- **Total: $500+/mo**

---

## Appendix: API Keys to Collect

Before implementation begins, gather:

- [ ] X/Twitter Bearer Token
- [ ] Anthropic API Key
- [ ] OpenRouter API Key
- [ ] Railway API Token (optional)
- [ ] Stripe Publishable + Secret Keys
- [ ] Resend API Key
- [ ] Upwork credentials (for scraping)
- [ ] GitHub Personal Access Token

---

*Last updated: 2026-02-01*
