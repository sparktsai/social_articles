# What AI Adoption Actually Looks Like Inside a Software Company

I recently heard about the current development practices of a software company from an employee who said they had been forced into retirement.

I’ll call it **Company A**.

This is not an assessment of whether Company A is adopting AI well or badly. Enterprise adoption rarely happens all at once.

It is simply a snapshot of what changed, what stayed the same, and what now sits somewhere in between.

## 1. Tools and Development Artifacts

**[T1] Work management**  
A Trello-like system manages work items. Work items are not directly linked to specifications or source code.

**[T2] Requirements**  
Requirements are maintained in an internal Wiki, including operating instructions, UI information, and database structures.

**[T3] UI**  
UI designs are created in Figma and manually introduced into the AI development context.

**[T4] Behavioral specification**  
GWT scenarios are stored in a separate document management system.

Engineers access them through a network drive. AI accesses them through MCP.

**[T5] AI coding**  
Claude Code is used for implementation.

**Before → Now:** shared enterprise token usage → individual employee keys.

The company can therefore track AI usage by employee, although those numbers are not currently used for performance evaluation or cost-productivity analysis.

**[T6] Testing**  
Playwright is used for E2E testing and produces persistent test reports.

---

## 2. Development Process

**[P0] PoC → Product Development**

Company A uses two different development modes.

During the **PoC stage**, development is primarily done through **Vibe Coding**. The purpose is to quickly determine whether an idea is viable enough to continue.

If the PoC is not selected for further investment, it may stop there.

If the company decides to develop it into a product, the PoC artifacts are not simply treated as the production baseline.

The formal development process starts again by creating:

**Figma → Wiki Specification → GWT → Product Development**

The product implementation is then rebuilt based on these formal artifacts.

So the lifecycle is closer to:

**Idea → Vibe Coding PoC → Investment Decision → Figma + Wiki + GWT → AI-assisted Product Development**

rather than one continuous PoC-to-production codebase.

**[P1] Development context**

For product development, there is no single system that automatically assembles the full context.

The engineer manually combines:

**Specification + Wiki Markdown + Figma UI + GWT + Repository**

and provides that context to AI.

**[P2] AI session continuity**

Development normally continues inside the same Claude Code session.

The session therefore carries part of the accumulated development context.

If the session is lost, much of that context has to be rebuilt. In practice, engineers rarely shut down their machines.

**[P3] AI skills**

Each engineer creates their own AI skills.

There is currently no unified company-wide skill set or standard AI development configuration.

**[P4] Testing flow**

**Before:**  
Qase → GWT → E2E Test

**Now:**  
GWT → Engineer + AI → Playwright E2E Code → Test Execution → Playwright Report

The engineer responsible for production implementation also generates and executes the E2E tests.

**[P5] Code review**

Review currently focuses on Claude Code execution results shown on screen, test results, and code diffs.

There is no separate persistent AI generation record, review decision document, or AI decision log.

**[P6] Git workflow**

**Before → Now:** largely unchanged.

The existing commit and merge process remains in place after AI adoption.

Some engineers proceed to commit and merge when all tests pass.

---

## 3. Organization and Engineering Roles

**[O1] Engineering structure**

**Before:**  
Frontend and backend responsibilities were separated, and multiple engineers handled different work items.

**Now:**  
Each engineer independently owns a product.

One engineer’s practical responsibility now includes:

**Frontend + Backend + Playwright E2E + Test Execution**

Most implementation is AI-generated.

The change is therefore larger than moving from frontend/backend specialization to traditional full-stack development.

The unit of responsibility has moved toward **one engineer owning one product delivery scope**.

---

## 4. Specification and Engineering Policy

**[S1] Specification approval**

Specifications are collaboratively written and reviewed by multiple people.

There is no formal approval gate or single final approver.

**[S2] Traceability**

Work items, Wiki specifications, Figma designs, GWT documents, source code, and AI sessions exist across different systems.

They are connected primarily through the engineer’s working process rather than through a unified traceability mechanism.

**[S3] PoC/Product boundary**

PoC development and formal product development intentionally use different engineering practices.

**PoC:** Vibe Coding for rapid validation.

**Product:** Figma + Wiki + GWT followed by formal implementation.

A positive PoC therefore triggers a new product-development cycle rather than automatically promoting the PoC implementation into production.

**[S4] Non-functional requirements**

There is no formal non-functional requirement design process covering areas such as performance, security, reliability, or scalability.

This condition existed before AI adoption.

AI has inherited the existing engineering environment rather than creating it.

---

## 5. AI Governance and Measurement

**[G1] AI configuration governance**

AI skills and working methods are defined independently by individual engineers rather than through a centralized standard.

**[G2] AI evidence**

Persistent evidence exists for some outputs, particularly Playwright test reports and Git history.

AI prompts, accumulated session context, generation decisions, and review decisions are not maintained as equivalent persistent engineering records.

**[G3] AI usage measurement**

**Before:** shared enterprise AI usage.

**Now:** individual employee keys and individual usage statistics.

However, usage is currently not correlated with cost, delivery throughput, defect rate, engineering productivity, or employee performance.

**[G4] Organizational AI KPI**

Company A has established a one-year AI adoption KPI:

**How much engineering headcount can be reduced.**

---

## A Transformation Moving at Different Speeds

Company A is not using one universal “AI development methodology.”

Even inside the same company, different stages operate differently.

**PoC:** Vibe Coding.

**Formal product development:** Figma + Wiki + GWT + AI GenCode.

**Implementation:** heavily changed by AI.

**Engineer ownership:** heavily changed.

**Testing:** changed.

**Git and review mechanics:** much closer to the pre-AI process.

**Requirements and engineering controls:** distributed across existing systems.

This does not make the transformation successful or unsuccessful.

It shows something more fundamental:

**Enterprise AI adoption is not one transformation. Different stages and different parts of the same software organization can evolve at very different speeds.**

That leaves several questions open.

What does AI ROI mean if the primary KPI is headcount reduction?

What does “full stack” mean when one engineer owns an entire product while AI generates most implementation?

Does Vibe Coding for PoC and specification-driven development for products create a useful boundary between exploration and engineering?

What does SDD mean when specification, GWT, UI, code, and AI context remain distributed across separate systems?

And what should governance review when implementation changes faster than the evidence and review processes around it?

#EnterpriseAI #AISoftwareDevelopment #SoftwareEngineering #AIAssistedDevelopment #AIAdoption #EngineeringTransformation
