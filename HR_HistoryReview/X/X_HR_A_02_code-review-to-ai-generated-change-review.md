# From Peer Inspection to AI-Generated Change Review: How Code Review Evolved

When people talk about code review today, they usually think about Pull Requests, comments on a diff, required checks, and approvals.

But code review did not begin as a platform workflow.

It began with a smaller question:

**Can another engineer find problems in this code before it becomes part of the system?**

That question is still alive. What changed over time was the review focus, the object being reviewed, and the outcome teams expected from the review.

## 1960s-1970s: Find defects through inspection

Early review was a structured human activity. A programmer wrote code, and other engineers inspected it for logic errors, missing cases, and misunderstandings. Formal inspection, especially the approach associated with Michael Fagan at IBM, turned this into a repeatable engineering process with preparation, inspection, rework, and follow-up.

Review centered on complete source-code listings, with engineers looking for defects and errors in logic.

This solved a basic but costly problem: mistakes that were invisible to the original programmer could be found and corrected before release.

The essential question was: **Does this code contain a problem?**

## 1980s-1990s: Preserve code quality

As systems and teams grew, review expanded beyond obvious defects. Engineers also examined naming, readability, structure, coupling, and maintainability. Code became not only executable logic but also a communication surface shared by future maintainers.

Reviewers still examined source code, but their attention widened to its internal structure: whether names were clear, responsibilities were well separated, and the design could be maintained consistently.

This addressed a problem that defect inspection alone could not solve: code might work today yet remain difficult for the rest of the team to understand and safely change tomorrow.

The question became: **Can other engineers safely understand and maintain this code?**

## 2000s: Understand the change

Version control made the change set visible. Reviewers no longer needed to reread an entire file or system. They could focus on what had been added, removed, or modified and examine the assumptions and side effects around that change.

The commit, change set, or diff became the review object. Reviewers focused on the correctness and impact of a specific modification instead of treating the entire codebase as one undifferentiated artifact.

This solved the problem of repeatedly reading complete files without a clear boundary around what had changed. It also made comments and revisions easier to connect to the exact change under discussion.

The question shifted from "Is this code correct?" to: **What changed, and is this change correct?**

## 2008-2015: Review becomes a Pull Request workflow

Pull Requests brought the branch, commits, diff, discussion, revisions, approvals, issue links, and merge decision into one workflow. Because a PR represented a proposed system change, reviewers increasingly considered interfaces, dependencies, architecture, and scope rather than inspecting individual lines alone.

The Pull Request became the review object, bringing code, context, discussion, revisions, automated results, and the merge decision into one place. Reviewers could judge not only whether the lines were correct, but whether the proposed change fit the system.

This solved the fragmentation between reviewing code and deciding whether to integrate it. Approval, requested revisions, rejection, and the reasoning behind those decisions became visible parts of the engineering record.

The governing question became: **Should this change become part of the system?**

## 2010s: Combine human judgment with automated evidence

Continuous Integration added builds, linting, static analysis, tests, and dependency checks to the review path. Machines could handle deterministic verification while people concentrated on requirements, architecture, tradeoffs, and side effects that required context.

Review expanded from the Pull Request itself to the evidence produced around it. Builds, linting, static analysis, tests, and dependency checks handled repeatable verification, while people concentrated on design, requirements, tradeoffs, and side effects.

This solved the problem of spending scarce human attention on deterministic checks that machines could perform more consistently. Review decisions could now combine contextual judgment with repeatable evidence.

Review confidence was no longer only "I read it." It also included: **The system checked it.**

## 2015-2022: Connect the change to its purpose

Enterprise and regulated development pushed review toward traceability. A change could be connected to a requirement, work item, modified files, test evidence, approval, and release record. This exposed an important limitation: clean code with passing checks can still solve the wrong problem.

The review object grew into an engineering change and its supporting chain of requirements, work items, modified files, test evidence, approvals, and release records. Reviewers examined whether the implementation covered the requirement and remained within scope.

This addressed a deeper problem: clean code and passing checks could still solve the wrong problem. Traceability made it possible to explain why a change existed and how its claimed purpose had been verified.

The central question became: **Can we prove that this change satisfies the requirement it claims to implement?**

## 2020s: Review risk and policy

Security and delivery automation widened the boundary again. Review now covers dependencies, permissions, infrastructure configuration, secrets, licenses, and organizational policies. Automated tools detect known patterns, but people still judge whether a valid configuration is appropriate in context.

Review now reaches beyond application code into configuration, dependencies, permissions, infrastructure, and deployment changes. Automated tools identify known security or policy violations, while people judge operational risk and whether a technically valid choice is appropriate in context.

This solved the problem of treating code correctness as sufficient for release. A change also had to be secure, compliant, operationally acceptable, and permitted to enter the delivery system.

The question expanded to: **What risk does this change introduce?**

## AI era: Verify intent alignment

AI can now generate code, tests, summaries, and review comments. The challenge is therefore larger than reviewing more code. If one AI interpretation produces all these artifacts, they may agree with each other while still misunderstanding the original request.

Generated code can match generated tests. The summary can match the generated code. Every automated check can pass. Yet the result may still exceed its scope or solve the wrong problem.

The review object is becoming the complete generated change, the evidence around it, and the authoritative human requirement behind it. Reviewers must determine whether the generated engineering outcome matches the intended problem and remains within scope.

This addresses the risk of internally consistent but externally incorrect work. Independent evidence and human judgment are needed to detect when generated code, tests, and explanations all agree with one another but not with the original intent.

The new question is: **Did the AI produce the change we intended, and can we prove it stayed within scope?**

## The history in one view

Code review evolved through a series of changing review objects:

**Source Code  
→ Code Quality  
→ Diff  
→ Pull Request  
→ Automated Evidence  
→ Requirement Traceability  
→ Security and Policy  
→ Intent Alignment**

The problem each stage could solve also changed:

**Undetected defects  
→ Code that was difficult to maintain  
→ Unclear change boundaries  
→ Fragmented merge decisions  
→ Repetitive manual checks  
→ Changes disconnected from requirements  
→ Unmanaged delivery risk  
→ Generated work misaligned with intent**

The history of code review is therefore not simply a move from manual work to automation, or from humans to AI.

It is a progression from reading code, to understanding change, to verifying evidence, to preserving intent.

AI does not remove the original review question: **Should this change become part of the system?**

It makes the answer depend on a clearer requirement, a smaller scope, independent evidence, and human judgment about whether the generated change belongs there at all.
