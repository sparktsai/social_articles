# From Acceptance Checklists to AI Evals: How Software Testing Evolved

When people talk about software testing today, they often start with Unit Tests.

JUnit. pytest. Jest.

Then Integration Tests, API Tests, and finally Selenium, Cypress, or Playwright for End-to-End testing.

But software testing did not begin with Unit Tests.

Its original question was much simpler:

**Did the system do what we expected it to do?**

That question has remained surprisingly stable for more than 70 years.

What changed was the size of the system, the complexity of its behavior, and the evidence required before we were willing to accept it.

## 1950s–1970s: Testing separates from debugging

In early software development, programming, testing, and debugging were often treated as closely related activities.

A programmer wrote code, ran it, found an error, fixed it, and ran it again.

Gradually, testing became a distinct engineering activity.

The basic structure was already familiar:

**Input → Execution → Expected Result → Actual Result → Acceptance**

The tools were primitive compared with today, but the logic was already there.

As systems became larger, testing also expanded beyond simply finding bugs.

Black-box testing, white-box testing, functional testing, verification, and validation all emerged around a broader question:

**How much confidence do we have that the system behaves as intended?**

This also produced one of software engineering's most persistent lessons:

Passing tests does not prove that software contains no defects.

It only provides evidence that the tested behaviors worked under the tested conditions.

That distinction is still important today, especially in AI.

## 1980s: Testing becomes documented engineering

By the 1980s, testing was no longer just a collection of test cases.

Formal test documentation began to include artifacts such as:

Test Plans, Test Designs, Test Cases, Test Procedures, Test Logs, Incident Reports, and Test Summary Reports.

This changed the role of testing.

A test was not only something that was executed.

It became something that could be reviewed, repeated, audited, and traced.

This is also where the distinction between **testing** and **quality assurance** becomes clearer.

Testing asks:

**Did this behavior produce the expected result?**

QA asks broader questions:

Were the requirements clear?

Were enough scenarios tested?

Were defects tracked?

Were changes retested?

Can we show evidence of what was verified?

Testing became part of a quality system.

## 1990s: Unit Testing moves verification next to the code

The next major shift was moving testing closer to implementation.

xUnit frameworks, JUnit, and similar tools made automated Unit Testing part of everyday development.

Instead of waiting until an entire application was complete, developers could verify individual functions, classes, and modules continuously.

The validation boundary became smaller:

**Function → Expected Result**

This dramatically reduced verification cost.

A developer no longer needed to manually retest an entire application after every small change.

Thousands of local behaviors could be checked automatically.

Then Test-Driven Development pushed testing even earlier.

Instead of:

**Code → Test**

TDD encouraged:

**Test → Code → Refactor**

Tests were no longer only verification artifacts.

They also became a form of **executable specification**.

## 2000s: Requirements start becoming executable

Agile development shortened delivery cycles.

Testing after months of development no longer worked well when software changed every day.

Continuous Integration moved automated tests directly into the delivery workflow.

A code change could trigger:

Build → Unit Test → Integration Test → Report

At the same time, Behavior-Driven Development connected business expectations with executable tests.

A requirement such as:

> A user should be locked after three failed login attempts.

could become:

```text
Given the user has failed login twice
When another incorrect password is entered
Then the account should be locked
```

Acceptance criteria started becoming machine-executable artifacts.

That was an important transition.

Testing was no longer only checking implementation.

It increasingly linked:

**Requirement → Behavior → Test → Evidence**

## 2000s–2010s: Testing expands toward E2E

Browser automation pushed the testing boundary outward again.

Unit Tests verify individual components.

Integration Tests verify components working together.

API Tests verify service behavior.

Contract Tests verify whether systems still honor agreed interfaces.

End-to-End Tests verify complete user journeys.

An E2E flow may look like:

**Browser → UI → API → Service → Database → Response → UI**

Tools such as Selenium, Cypress, and Playwright made this increasingly automated.

But E2E testing also revealed another engineering reality:

The closer a test gets to the real system, the more expensive and fragile it usually becomes.

Modern testing therefore became layered rather than simply "more E2E."

A typical stack might include:

Unit  
Component  
Integration  
API  
Contract  
System  
E2E  
Acceptance

Each layer answers a different question at a different cost.

## DevOps: Testing becomes a delivery gate

With CI/CD, testing moved from being a development activity to becoming part of software delivery infrastructure.

A modern pipeline may look like:

**Commit  
→ Build  
→ Static Analysis  
→ Unit Test  
→ Integration Test  
→ Contract Test  
→ Security Scan  
→ E2E  
→ Deploy  
→ Smoke Test  
→ Monitoring**

Testing is now distributed across the Software Development Lifecycle.

QA is no longer simply a team waiting at the end to find bugs.

Quality evidence is generated continuously.

## Then AI changed the problem again

If AI generates ordinary software, traditional testing still works.

AI-generated functions can still have Unit Tests.

AI-modified APIs can still have Integration and Contract Tests.

AI-generated features can still be tested through E2E flows.

In fact, automated testing may become even more important when code is generated faster than humans can inspect every line.

But testing changes significantly when **the system being tested is itself AI**.

Traditional software often allows us to write:

```text
Input: 2 + 2
Expected: 4
```

An LLM may instead receive:

> Summarize this contract.

There may be many acceptable answers.

An Agent may:

Retrieve information, reason, call tools, modify state, observe results, make another decision, and continue until a task is complete.

Different execution paths may all be acceptable.

The simple model:

**Expected Result == Actual Result**

is no longer enough.

AI testing increasingly requires artifacts such as:

Eval datasets  
Scenarios  
Rubrics  
Graders  
Thresholds  
Failure taxonomies  
Model and prompt versions  
Tool-call traces  
Regression baselines  
Acceptance reports

A result may look more like:

**Task completion ≥ threshold  
Factuality ≥ threshold  
Unsafe behavior = 0  
Tool-call correctness ≥ threshold  
Regression ≤ tolerance**

And sometimes the same scenario must be executed multiple times because the system is probabilistic.

## From E2E to Agent Evals

Agentic systems push the testing boundary outward once again.

Testing a single prompt and response is not enough when the system can take multiple actions.

We may need to test:

Prompt behavior  
Retrieval quality  
Tool selection  
Tool arguments  
Intermediate decisions  
State changes  
Recovery behavior  
Final task completion

This is effectively a new form of End-to-End testing.

The difference is that the execution path itself may not be deterministic.

## Seventy years later, the question is still the same

If we remove the names of all the tools—JUnit, pytest, Selenium, Playwright, Pact, CI/CD, LLM Evals—the core question has barely changed:

**How do we know this system did what we intended it to do?**

What changed is the meaning of "system."

First it was a program.

Then a function.

Then an application.

Then distributed services.

Then an entire production workflow.

Now it may be an AI Agent that interprets information, makes decisions, calls tools, and changes external state.

So the history of software testing is not simply:

**Manual → Automated**

or:

**Unit → Integration → E2E**

It is closer to:

**Acceptance  
→ Test Cases  
→ Structured Test Documentation  
→ Automated Unit Tests  
→ Executable Specifications  
→ Continuous Verification  
→ End-to-End Validation  
→ AI Evaluation**

For decades, software engineering has been turning:

**"I think it works."**

into:

**"Show me the evidence."**

AI does not change that principle.

It changes what evidence we need.
