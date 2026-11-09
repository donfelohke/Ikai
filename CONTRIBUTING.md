# Contributing to IKAI

Before proposing an experiment, document:
- The research question and intended benefit.
- What data is needed and why.
- Whether data is personal, sensitive, identifiable, or derived.
- Where processing occurs and which components can access data.
- Consent, notice, retention, deletion, and withdrawal expectations.
- Potential misuse, failure modes, and a way to stop the experiment.
- The method for checking expected versus observed behaviour.
- Whether AI tools are used, which authorised input classes are processed, and what human review is performed.

Use synthetic or non-identifying data when it is sufficient. Do not add real participant data, recordings, credentials, or private logs to Git. Do not describe a prototype as validated merely because it runs. Follow [AI Assistance, Research Integrity and Participant Privacy](AI-ASSISTED-DEVELOPMENT.md); never send identifiable or sensitive participant material to an external AI service without documented authority and consent.

Pull requests should include tests or inspection evidence, limitations, and a clear statement of any unverified privacy assumptions.
