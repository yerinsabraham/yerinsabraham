# Yerins Abraham

**AI/Application Engineer.** I build AI systems that take real actions in production, and the controls that make that safe.

Six-plus years shipping backend and full-stack software. The last stretch has been agents, retrieval and evaluation, on top of a core banking platform and a multi-product API I still run.

Kigali, Nigeria and Dubai at different times. Remote worldwide, and I travel.

---

## What I actually build

**[Lira Intelligence](https://liraintelligence.com)** is an AI support agent that answers from a company's own knowledge base and then does the thing: freeze the card, check the transaction, open the ticket. The interesting part is not the answering. It is letting a language model take privileged actions without that being reckless.

So it has:

- **Production RAG** on Qdrant. Hybrid search, vector plus keyword, ranked by source authority and filtered by knowledge-base segment. It degrades to keyword retrieval when the vector store is down instead of failing the turn.
- **A seven-tier risk model** on every tool, from `read_public` to `human_only`, plus maker-checker approval: the agent parks a privileged action, a second person authorises it out of band, and the tool executes server-side and writes back into the conversation. An approver acts hours later, when the customer's socket is long gone.
- **An MCP gateway** so a customer can plug in their own tool server. Off by default, KMS-backed credentials, SSRF protection through DNS resolution and private-IP blocking, per-tool rate limits, full config audit trail. → [how and why I built it this way](https://yerinsabraham.com/engineering/mcp-gateway)
- **A realtime voice agent** in Python on Pipecat with AWS Nova Sonic.
- **An eval harness** that fails the build on regression. → [open sourced, and now the CI half of trackline](https://github.com/yerinsabraham/trackline)

It runs on one Fastify service on AWS serving four products from 155 service modules and a 46-model PostgreSQL schema, isolated by table prefix and product-scoped JWT claims.

Separately I lead backend on a **production core banking platform** in .NET 8. Over the 30 days to 9 September 2026 it served 65,942 requests with **two server errors**, p95 284ms. That same governed agent now runs inside its API.

---

## Most of my work is private, so here is the public proof

Client systems and commercial products do not go on GitHub. What I can do is open source the parts that carry no customer data, and write up the architecture.

| | |
| --- | --- |
| **[trackline](https://github.com/yerinsabraham/trackline)** | An alignment layer for AI agents. Checks whether an agent's actions still match the task, the rules and the evidence it was given: beside a local coding agent while it works, and across production traces. One engine, two surfaces. The CI eval gate is the first working component, and its safety metrics carry an absolute floor of zero, so an agent that starts complying with prompt injection cannot pass on tolerance. → [why I am building it](https://yerinsabraham.com/engineering/nothing-notices-when-an-agent-drifts) |
| **[agentfile](https://github.com/yerinsabraham/agentfile)** | Writes the context file an AI coding agent reads before it touches your code. No backend, no keys, no model call. |
| **[liracall](https://github.com/yerinsabraham/liracall)** | An AI voice agent that feels like a real phone call. Native call screen, live cloud backend. |
| **[cvault](https://github.com/yerinsabraham/cvault)** | Privacy-first VPN on WireGuard. Backend, desktop client, JavaScript SDK and web demo. |
| **[yerinsabraham.com](https://github.com/yerinsabraham/yerinsabraham_site)** | My site, and where the engineering write-ups live. |

The contribution graph counts private work, which is most of it.

---

## Stack

**AI** RAG, agents, tool calling, MCP, evals, guardrails, prompt-injection defence, realtime voice · Anthropic Claude, OpenAI, AWS Bedrock, Nova Sonic, Pipecat, Qdrant

**Backend** TypeScript, Node.js, Fastify, Python, C#/.NET 8, Go · PostgreSQL, Prisma, DynamoDB, Redis, Kafka

**Cloud** AWS (EC2, ECS, RDS, S3, KMS, Secrets Manager, Bedrock), Docker, GitHub Actions, CI/CD

**Frontend** React, Next.js, TypeScript, Flutter

---

## Also

I am a medical doctor, and I am building **[Oystar](https://oystar.app)**, which carries a patient's case from a frontline clinic to the right specialist and brings the clinical answer back. Live in Rwanda. Patients who never arrive get flagged instead of lost, and the patient needs no phone and no app.

I run **[Creovine Academy](https://academy.creovine.com)**, teaching engineers to work with AI. 120+ people so far.

Outside all of it I draw, in pen and ink, at some scale.

---

**Open to senior AI and backend engineering roles.** Remote worldwide, EOR or contract.

**yerinssaibs@gmail.com** · [yerinsabraham.com](https://yerinsabraham.com) · [LinkedIn](https://linkedin.com/in/yerinsabraham) · [X](https://x.com/yerinsabraham)
