# FormDesk AI

### Local-first pre-application readiness assistant for Indian cyber cafés

> **Project status:** Direction locked for MLH Global Hack Week 2026 ---
> Week 2: Side Hustle\
> **Stage:** Pre-assessment / pre-project specification\
> **Build window:** 7 days\
> **Primary users:** Cyber-café operators who help candidates complete
> examination and recruitment applications\
> **Secondary users:** Candidates waiting to submit an application\
> **Core principle:** Identify missing information before a candidate
> reaches the form-filling desk.

------------------------------------------------------------------------

## 1. Project summary

FormDesk AI is a QR-based, local-first pre-application readiness system
for cyber cafés and document-service shops in India.

During peak examination and recruitment application periods, candidates
may wait in a queue to get help completing an online form. Some discover
only when they reach the operator that they are missing a document, do
not know a required detail, or need to clarify a requirement. This can
waste the candidate's time and the operator's time, interrupt the queue,
and require the candidate to return later.

FormDesk AI moves a basic readiness check into the waiting area:

1.  The café displays a QR code.
2.  A candidate scans it using their phone and opens a local web page.
3.  The candidate selects the relevant examination or application type.
4.  The system displays the configured requirements and checklist.
5.  The candidate confirms available documents and provides the
    requested information.
6.  Optional local AI helps extract information from permitted files and
    flags missing or ambiguous fields.
7.  The candidate receives a readiness result.
8.  The operator sees the candidate's status in a queue dashboard and
    reviews the information when the candidate reaches the desk.

The system is intended to reduce avoidable preparation delays. It does
**not** guarantee official eligibility, replace the examination
authority, or submit an official application automatically.

## 2. Origin of the idea

The idea is based on an observed pattern in Indian cyber cafés during
busy examination and recruitment application seasons: candidates can
queue for form-filling assistance and discover late in the process that
they lack required documents or information.

This observation motivates the project, but it is not yet proof of how
often the problem occurs across cafés. The first phase should validate
the workflow with an operator if possible.

### Problem statement

During peak examination and recruitment application periods, cyber cafés
may lose service time when candidates reach the form-filling desk
without all required documents or information. Because these gaps are
discovered late, candidates may need to retrieve missing items, clarify
details, or return later, interrupting the operator's workflow and
reducing service capacity.

### The problem we are solving

**Identify missing documents and information while a candidate is
waiting, before the candidate begins assisted form filling.**

### Problems we are not trying to solve in the MVP

-   Replacing government or examination-authority portals.
-   Guaranteeing eligibility or deciding a candidate's official
    eligibility.
-   Automatically submitting applications.
-   Supporting every examination and recruitment form in India.
-   Building a complete cyber-café billing, printing, or inventory
    system.
-   Integrating with every third-party application platform.
-   Storing identity documents indefinitely.
-   Replacing the operator's verification and judgment.

## 3. Target users

### Primary user: Cyber-café operator

A shop owner or operator who helps candidates complete online
examination, recruitment, or related applications. The operator needs to
prepare candidates before the assisted form-filling step, avoid repeated
clarification, and keep the queue understandable.

### Secondary user: Candidate

A candidate who is waiting for help and wants to know which documents
and details are required before reaching the operator.

### Initial target segment

Start with **one cyber café and one examination/application category**
if access is available. A narrow initial segment is easier to validate
and build than a universal application checklist.

## 4. Assumptions to validate

These are hypotheses, not established facts.

  -----------------------------------------------------------------------
  ID                      Hypothesis              How to validate
  ----------------------- ----------------------- -----------------------
  H1                      Candidates sometimes    Ask an operator about
                          reach the desk with     recent cases and
                          missing documents or    observe the current
                          information.            workflow.

  H2                      Missing information is  Map the current process
                          often discovered after  and record where gaps
                          the candidate has       are discovered.
                          waited.                 

  H3                      A pre-check during      Compare similar tasks
                          waiting can reduce      with and without the
                          avoidable               pre-check.
                          interruptions.          

  H4                      Operators can use a     Test a clickable or
                          simple queue status     working prototype with
                          without disrupting      an operator.
                          their work.             

  H5                      Local AI can improve    Compare local AI output
                          extraction or           with a deterministic
                          interpretation enough   checklist and verified
                          to justify its use.     reference data.

  H6                      Local-first processing  Ask about connectivity,
                          is valuable to the      privacy, cost, and
                          target user.            willingness to use the
                                                  system.

  H7                      A café may pay for a    Seek direct feedback
                          tool that measurably    and, if possible, a
                          improves throughput or  paid pilot or explicit
                          reduces rework.         purchase commitment.
  -----------------------------------------------------------------------

Do not describe any hypothesis as validated until evidence has been
collected.

## 5. Proposed user workflow

### Candidate workflow

1.  Scan the QR code displayed in the café.
2.  Open the web page served by the café's local network.
3.  Select the examination/application from the supported list.
4.  Read the requirements and confirm the relevant information.
5.  Tick off available documents and provide requested fields.
6.  Optionally provide permitted files for local extraction, if that
    feature is enabled.
7.  Review the system's findings.
8.  Receive one of these statuses:
    -   **Ready for operator review**
    -   **Action required**
    -   **Manual review required**
9.  Follow the instructions and wait for the operator to call them.

### Operator workflow

1.  Open the local operator dashboard.
2.  See candidates who have completed the pre-check and their readiness
    statuses.
3.  Review the missing-information summary.
4.  Call an appropriate candidate when ready.
5.  Verify the candidate's information and documents.
6.  Complete the official application using the relevant official
    portal.
7.  Mark the local job as completed or needing follow-up.

### Important product behavior

-   A candidate who has not completed the checklist must not be
    represented as ready.
-   A missing field must not be silently filled with a guess.
-   AI output must remain editable and subject to human review.
-   The system must distinguish "documents appear to be present" from
    "candidate is officially eligible."
-   Official requirements must be tied to a known source and review
    date.
-   If a requirement is uncertain, outdated, or ambiguous, show **manual
    review required**.
-   A QR code is only an entry point; the phone must be able to reach
    the café's local server through the local network.

## 6. Readiness statuses and eligibility boundaries

### Status 1: Ready for operator review

The configured checklist appears complete and the preliminary checks
passed. This does not guarantee official eligibility or acceptance by
the examination authority.

### Status 2: Action required

A required document, answer, or information field appears to be missing.
The system should explain what is missing and what the candidate can do
next.

### Status 3: Manual review required

Information conflicts, a rule is ambiguous, the document could not be
read reliably, or an operator must interpret the official requirement.

### Eligibility policy

-   Use structured, verified rules for straightforward checks such as
    required fields and explicitly configured age/date calculations.
-   Use AI to assist with unstructured text or document extraction, not
    as the final authority for consequential eligibility decisions.
-   Never invent eligibility criteria.
-   Do not infer eligibility from document presence alone.
-   Display the official source and its last-reviewed date for each
    supported examination configuration.
-   If the source cannot be verified or may be outdated, stop short of
    an eligibility claim.

## 7. MVP scope

### Must have

-   Mobile-friendly candidate web page opened by QR code.
-   One supported examination/application checklist.
-   Candidate questionnaire and document-availability checklist.
-   Local operator dashboard.
-   Candidate queue with readiness status.
-   Rule-based required-field and checklist validation.
-   Clear missing/ambiguous-information messages.
-   Human review and correction.
-   Local persistence for the minimum necessary job data.
-   Basic audit trail for status changes.
-   A repeatable test dataset using synthetic candidate records.
-   A demo that shows the full flow from QR entry to operator review.

### Include if time permits

-   Local open-weight model for extracting structured fields from sample
    text or permitted documents.
-   Local OCR for document text, if needed and feasible.
-   Export of a readiness summary.
-   Hindi/English interface or bilingual guidance for the selected user
    group.
-   Configurable checklist loaded from a versioned local file.
-   A simple reminder or queue notification inside the operator
    dashboard.

### Out of scope for this one-week build

-   Automatic submission to official portals.
-   Login or integration with multiple government portals.
-   Universal coverage of all exams, recruitment boards, and application
    types.
-   Payment processing or café billing.
-   Automated identity verification or authenticity determination.
-   Autonomous eligibility decisions.
-   Cloud storage of identity documents.
-   Production deployment handling real sensitive documents before
    security and legal review.

## 8. Open-AI strategy

The challenge requires open AI to be at the core of the project. A
closed model API should not be the main engine of the MVP.

### Proposed approach

-   Run a suitable open-weight model locally through Ollama.
-   Use conventional code for deterministic validation, status
    management, and queue operations.
-   Use OCR where text recognition is required; do not use an LLM for
    simple OCR if a more appropriate tool is available.
-   Use the model only where it adds value, such as turning unstructured
    candidate-provided text into structured fields or explaining
    ambiguous input.
-   Require human review before extracted information is used for a
    consequential application.
-   Benchmark the selected model on a small, representative test set
    before claiming it is suitable.

### Why open AI may matter

-   **Local processing:** candidate-provided data can be processed
    without sending it to an external model provider, provided the whole
    application is configured accordingly.
-   **Reduced API dependence:** routine inference does not incur
    per-request hosted-model API fees.
-   **Offline potential:** after setup and model download, the core
    local workflow can operate without external internet if all required
    assets and services are available locally.
-   **Model flexibility:** the model can be replaced or evaluated
    against alternatives.
-   **Customization:** prompts, schemas, evaluation cases, and
    potentially model behavior can be adapted to the chosen workflow.

These are intended benefits to verify, not claims that have already been
proven. Open-weight does not automatically mean open-source, free of all
costs, or unrestricted for commercial use. Check the chosen model's
license and hardware requirements. Local inference alone does not
guarantee privacy; logs, uploads, backups, and storage must also be
controlled.

### AI fallback behavior

If the model is unavailable, times out, or returns malformed output:

1.  Do not mark the candidate ready based on the failed AI result.
2.  Preserve the candidate's manual checklist answers.
3.  Show that automated extraction was unavailable.
4.  Allow the operator to review the record manually.
5.  Log the failure without unnecessarily logging sensitive document
    contents.

## 9. Proposed architecture

Keep the architecture simple for a one-week prototype.

``` text
Candidate phone
    |
    | QR code / local network
    v
Mobile-friendly web frontend
    |
    v
Local backend (FastAPI)
    |------------------------------|
    v                              v
Checklist and rules engine     Local AI/OCR pipeline
    |                              |
    |                              v
    |                         Structured draft fields
    |                              |
    |------------------------------|
                   |
                   v
        Human review and correction
                   |
                   v
       Local database / job queue
                   |
                   v
         Operator dashboard
```

### Suggested technology

-   **Frontend:** React + Tailwind CSS
-   **Backend:** Python + FastAPI
-   **Database:** SQLite for the prototype
-   **Local model runtime:** Ollama with a suitable open-weight model
-   **Document processing:** OCR only if the MVP needs it
-   **Testing:** synthetic fixtures, field-level accuracy checks,
    workflow timing, and failure-case tests

Do not add agents, vector databases, or multi-model orchestration unless
a demonstrated requirement needs them. The first objective is a reliable
workflow, not architectural complexity.

## 10. Baseline and evaluation plan

We do not yet have measured baseline data. Collect it before making
performance claims.

### Baseline metrics

  -----------------------------------------------------------------------
  Metric                              Definition
  ----------------------------------- -----------------------------------
  Preparation-related interruption    Candidates who reach the desk with
  rate                                missing required information or
                                      documents, per 100 candidates

  Desk-side preparation time          Time spent resolving missing
                                      information after the candidate
                                      reaches the operator

  Total service time                  Time from the start of assisted
                                      preparation to a review-ready
                                      application, excluding unrelated
                                      waiting

  Rework rate                         Share of candidate jobs that
                                      require repeated information
                                      collection or correction

  Readiness-check accuracy            Agreement between the pre-check
                                      result and a verified manual review

  Critical omissions                  Required items missed by the
                                      pre-check

  Candidate completion rate           Share of candidates who complete
                                      the pre-check after starting it

  Operator adoption                   Whether the operator can use the
                                      dashboard during normal work
                                      without excessive extra steps
  -----------------------------------------------------------------------

### Provisional MVP targets

These are engineering targets to test, not official MLH requirements or
industry benchmarks.

-   Reduce preparation-related interruptions by at least 30% in a
    controlled comparison.
-   Reduce desk-side preparation time by at least 30%.
-   Achieve at least 95% agreement on the defined readiness test set.
-   Have no critical omission in the defined test set; investigate any
    such failure before further use.
-   Show the status of every candidate who completes the pre-check.
-   Demonstrate that the core workflow works on the local network
    without external internet once installed, if offline operation is
    claimed.

A small test set is useful for discovering failure modes but cannot
prove production reliability. Report sample size, test composition, and
limitations. Do not claim statistical significance from a handful of
users.

## 11. Privacy, security, and responsible use

The project may involve sensitive personal information. The prototype
should minimize what it collects.

-   Use synthetic candidate data by default during development and
    demonstrations.
-   Do not require an identity-document upload if a checklist or
    self-declaration is sufficient.
-   Collect only information necessary for the chosen pre-check.
-   Do not store full identity-document images by default.
-   If files are processed, define whether they remain in memory or are
    temporarily written to disk, and delete temporary files promptly.
-   Do not expose the operator dashboard to the public internet.
-   Use a private local network and protect operator access.
-   Avoid putting personal data in logs, model prompts retained by other
    services, or session-sharing links.
-   Provide a clear notice explaining the purpose of the pre-check and
    how data is handled.
-   Provide a way to remove a candidate's temporary job record.
-   Do not present the system as an official government service.
-   Do not promise legal compliance without appropriate review.
-   Do not use AI to make final eligibility decisions or submit forms
    without human review.

## 12. One-week implementation plan

### Day 1 --- Define and validate

-   Finalize one examination/application category.
-   Find the official source for its current requirements.
-   Map the candidate and operator workflow.
-   If feasible, speak to one cyber-café operator.
-   Define the test cases and baseline measurement method.

### Day 2 --- Build the core workflow

-   Create the candidate landing page and checklist.
-   Create the FastAPI endpoints and SQLite schema.
-   Create the operator queue and statuses.
-   Add deterministic required-field validation.

### Day 3 --- Add open AI

-   Set up local inference with Ollama and a suitable open-weight model.
-   Define a strict structured output schema.
-   Test extraction using synthetic sample data.
-   Add malformed-output and model-unavailable handling.

### Day 4 --- Integrate and review

-   Connect AI results to the candidate workflow.
-   Add field-level review and correction.
-   Ensure missing or ambiguous values are flagged.
-   Keep deterministic checks separate from AI-generated
    interpretations.

### Day 5 --- Complete the MVP

-   Add the QR entry point and local-network access.
-   Add queue updates and minimal audit history.
-   Add basic privacy and deletion behavior.
-   Test the complete happy path and common failure paths.

### Day 6 --- Evaluate

-   Run the defined synthetic test set.
-   Measure extraction quality, readiness agreement, timing, and
    failures.
-   Compare against the manual baseline where observations are
    available.
-   Seek operator feedback if possible.
-   Fix the highest-impact defects.

### Day 7 --- Submit

-   Clean up the repository and setup instructions.
-   Record a short demonstration.
-   Document the open-AI advantage and actual limitations.
-   Save a relevant DevRelay agent session if available.
-   Prepare the MLH challenge post with repository, demo, evaluation
    results, and session link if appropriate.

## 13. Definition of done

The MVP is ready to submit when:

-   [ ] A candidate can open the local web page through the QR code.
-   [ ] One supported application checklist can be completed.
-   [ ] The backend validates required fields and identifies missing
    information.
-   [ ] The operator can see and review the candidate's status.
-   [ ] AI extraction, if included, uses an open-weight model and can be
    tested independently.
-   [ ] AI failures do not silently produce a "ready" result.
-   [ ] Candidate data is handled according to the prototype's stated
    privacy behavior.
-   [ ] Synthetic test cases cover complete, incomplete, ambiguous, and
    malformed inputs.
-   [ ] The README and demo distinguish verified results from
    assumptions.
-   [ ] The repository can be run from documented setup instructions.

## 14. Guidance for coding agents and querying/research agents

This section is intended to be read before doing work on the project.

### Shared project context

You are assisting with **FormDesk AI**, a one-week MLH Global Hack Week
2026 Week 2 Side Hustle project. The goal is to help cyber cafés
identify missing candidate information before assisted examination or
recruitment form filling begins. Candidates enter through a QR code,
complete a readiness checklist, and receive a status. An operator sees
the status in a local dashboard.

### Non-negotiable constraints

1.  Do not change the target problem or turn this into a generic chatbot
    without asking the project owner.
2.  Do not expand the MVP to multiple portals, automatic submissions,
    payments, or a complete café-management suite.
3.  Open-weight AI must materially contribute to the prototype; do not
    replace the main AI path with a closed API.
4.  Use deterministic code for deterministic rules.
5.  Treat AI outputs as drafts that require validation and, where
    appropriate, human review.
6.  Never invent official requirements. Use a current, traceable
    official source for the selected application.
7.  Never claim that the tool confirms official eligibility.
8.  Use synthetic data unless the project owner has approved a safe,
    appropriate test dataset.
9.  Do not add unnecessary dependencies or architecture.
10. Keep this README updated when scope, assumptions, or decisions
    change.

### Instructions for the coding agent

Before coding:

1.  Read this README fully.
2.  Inspect the existing repository and report what already exists.
3.  Identify the smallest next implementation step.
4.  State the files to create or modify and why.
5.  Implement incrementally and run relevant tests.
6.  Report what changed, what was tested, what failed, and what remains.

When uncertain, ask before making a scope-changing decision. Prefer
simple, maintainable code and explicit failure handling. Do not claim a
test passed unless it was run.

### Instructions for the querying/research agent

The querying agent is responsible for research and evidence, not for
silently changing the product scope.

For research tasks:

1.  Prefer official examination/recruitment notifications and official
    instructions for requirements and dates.
2.  Record the source URL, publication or effective date when available,
    access date, and the exact requirement supported.
3.  Distinguish verified facts, user observations, assumptions, and
    recommendations.
4.  Do not infer eligibility rules from unofficial summaries when an
    official source is available.
5.  Do not collect or expose real candidates' personal data.
6.  Research existing cyber-café workflows and competing tools without
    claiming demand has been validated from a single anecdote.
7.  Return concise findings, sources, confidence, implications for the
    MVP, and unresolved questions.
8.  If sources conflict or are outdated, flag the conflict and recommend
    manual review.

### Instructions for DevRelay and session-aware agents

Use DevRelay where it is available and configured to preserve a useful
record of development work. A session record is optional supporting
evidence for the challenge, not a substitute for working code, testing,
or the final submission.

When saving or sharing a session:

-   Keep the session relevant to the problem, architecture,
    implementation, and evaluation.
-   Never include API keys, passwords, authentication tokens, or
    unnecessary candidate information.
-   Verify that the saved session link works before including it in the
    post.
-   Do not claim DevRelay is part of the product architecture unless the
    application actually depends on it.

### Required agent response format for substantial tasks

For each substantial task, report:

1.  **Goal**
2.  **Evidence or assumptions**
3.  **Plan**
4.  **Changes made**
5.  **Tests and results**
6.  **Risks or unresolved questions**
7.  **Next recommended step**

## 15. Submission narrative outline

The final challenge post should tell the story in this order:

1.  **The observed problem:** candidates wait in line and may discover
    missing requirements only when they reach the cyber-café operator.
2.  **The intervention:** a QR-based pre-check identifies missing
    information while the candidate waits.
3.  **How it works:** candidate checklist, local processing, readiness
    status, and operator queue.
4.  **Why open AI matters:** local extraction, offline potential,
    reduced API dependence, and model flexibility---only where
    demonstrated.
5.  **Evaluation:** test set, baseline, measured results, limitations,
    and failure cases.
6.  **User feedback:** what an operator or candidate said, if real
    feedback was obtained.
7.  **What comes next:** improvements supported by evidence.

Writing quality is heavily weighted in the supplied challenge criteria,
so make the post understandable to a reader who is not familiar with the
codebase. Do not overstate performance, adoption, privacy, or commercial
viability.

## 16. Current decisions and open questions

### Decisions locked

-   Project name: **FormDesk AI**
-   Target setting: Indian cyber cafés and document-service shops
-   Core problem: late discovery of missing information or documents
    before assisted application filling
-   Primary interaction: QR code → candidate readiness check → operator
    queue
-   AI approach: open-weight model with local inference where it
    provides measurable value
-   Core safeguards: human review, no invented requirements, no
    autonomous official eligibility decision
-   Timebox: one week
-   Default test data: synthetic

### Still to decide or validate

-   Which single examination/application category will be supported
    first?
-   Which official source will define its requirements?
-   Can a cyber-café operator validate the problem or test the
    prototype?
-   Does local AI materially outperform a deterministic checklist for
    any part of the workflow?
-   Which OCR/model combination is accurate enough on the available
    hardware?
-   What baseline and measured results can be collected during the week?
-   What, if anything, would the target operator pay for?

These are intentionally open. Do not resolve them by guessing; gather
evidence or record an explicit prototype assumption.

------------------------------------------------------------------------

## Final project principle

**FormDesk AI should help candidates discover what is missing before
they reach the desk---not pretend to be the examination authority.**

Build the smallest reliable workflow, use open-weight AI where it
provides a defensible advantage, measure the result, and communicate
honestly what has and has not been validated.
