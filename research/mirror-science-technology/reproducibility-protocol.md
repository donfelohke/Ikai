# Computational Reproducibility Protocol

**Status:** RESEARCH / PROPOSED CHECKLIST  
**Purpose:** Make computational claims inspectable and bounded. This is not a certification.

## 1. State the claim

- What exact result, behaviour, measurement, or build is claimed?
- What counts as successful reproduction?
- What observations would contradict the claim?
- What is outside scope?

Avoid broad statements such as “the system works” when only one test or configuration was examined.

## 2. Preserve provenance

Record, where applicable:

- Repository URL and exact commit or release.
- Source hashes and relevant patch.
- Operating system, architecture, kernel, hardware, and firmware assumptions.
- Toolchain and dependency versions.
- Build flags, environment variables, locale, timezone, timestamps, and network inputs.
- Dataset identifiers, licences, collection method, transformations, and exclusions.
- Exact commands, scripts, configuration, and expected outputs.
- Test date, operator, logs, exit status, and deviations.

Do not publish credentials, private identifiers, personal data, or secrets in logs. Redact securely and document the redaction.

## 3. Separate levels of reproducibility

- **Procedural repeatability:** documented steps can be executed again in the same stated setup.
- **Computational reproducibility:** the same data and analysis steps yield materially equivalent results under declared conditions.
- **Bit-for-bit build reproducibility:** independent builds from specified inputs produce identical output bytes.
- **Independent replication:** a separate attempt, potentially by a different team or using new data, tests whether a finding generalises or recurs.

Terminology varies by field. State the definition used and do not claim one level from evidence of another.

## 4. Execute and record

1. Start from a clean, documented environment.
2. Verify source and input identities.
3. Execute the documented procedure without undocumented intervention.
4. Capture standard output, errors, exit codes, relevant hashes, and deviations.
5. Repeat from a clean state where practical.
6. Compare actual and expected results using a stated comparison rule.
7. Investigate nondeterminism, environmental dependencies, and failed runs.
8. Have an independent reviewer assess the procedure when feasible.

## 5. Report honestly

State what was and was not tested; exact environment and input versions; whether results matched, partially matched, or failed; differences and unresolved causes; external dependencies; whether independent reproduction occurred; and limitations on generalising the result.

A passing automated test is evidence only for its coverage, assertions, and execution context. It does not prove the absence of bugs or establish system-wide security.

## 6. Data and ethical constraints

Openness does not override privacy, safety, licences, contractual restrictions, or community permissions. If data cannot be shared, document why, provide non-sensitive metadata where appropriate, and explain controlled-access or synthetic-data alternatives. Do not claim independent reproduction where essential inputs are unavailable.

## 7. Minimal experiment record

- Experiment ID:
- Claim under test:
- Status:
- Repository and commit:
- Environment:
- Inputs and dataset version:
- Commands and procedure:
- Expected result:
- Actual result:
- Logs and hashes:
- Repeat count:
- Independent reproduction:
- Differences and failures:
- Limitations:
- Data, licence, and ethics constraints:
- Author and date:
- Reviewer and date:

## 8. Acceptance checklist

- [ ] Claim and scope are precise.
- [ ] Source and inputs are identifiable.
- [ ] Dependencies and environment are documented.
- [ ] Procedure is executable by another person.
- [ ] Expected and actual outputs are recorded.
- [ ] Failures and deviations are preserved.
- [ ] Privacy and licensing constraints are addressed.
- [ ] Conclusion does not exceed the evidence.
