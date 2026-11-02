# ECZ-ID Trust Delta

Compare normalized GitHub workflow authority/currentness evidence with a reviewed baseline without retaining raw source or secret names.

**Start without an ECZ-ID account or API key.** ECZ-ID does not charge to install or use this public Action; GitHub Actions runner usage follows your GitHub plan.

## Outcome

Answer what changed since a reviewed workflow/Agentic authority baseline without pretending no-baseline means unchanged.

## Run it now

Create `.github/workflows/eczid.yml`, paste this complete first-run workflow, commit it, then run it from the **Actions** tab.

```yaml
name: ECZ-ID Trust Delta

on:
  workflow_dispatch:

permissions:
  contents: read

jobs:
  eczid:
    runs-on: ubuntu-latest
    steps:
      - name: Check out repository
        uses: actions/checkout@v7

      - uses: EcoCitizenz-Ltd/eczid-trust-delta@v1
```

### First-run path

1. Add the workflow above.
2. Run it manually with **Run workflow**.
3. Open the job and review the ECZ-ID Job Summary.
4. Use the generated local JSON report and outputs below for your own policy or follow-up automation.
5. If persistent machine identity is useful, [choose the right free ECZ-ID Passport](https://developers.ecocitizenz.com/get-started/free-passport/?utm_source=github&utm_medium=action-readme&utm_campaign=github-actions&utm_content=eczid-trust-delta&ecz_source=github&ecz_surface=eczid-trust-delta&intent=free-passport); identity is optional and does not change the technical result.

## Minimal Action step

Already have a workflow? Add only this step:

```yaml
- uses: EcoCitizenz-Ltd/eczid-trust-delta@v1
```

## Inputs

| Input | Required | Default | Description |
|---|---:|---|---|
| `baseline-path` | No | `.eczid/github-trust-snapshot.json` | Reviewed baseline snapshot path. |
| `report-path` | No | `eczid-trust-delta.json` | Path for the delta report. |
| `proposal-path` | No | `.eczid/github-trust-snapshot.proposed.json` | Path for the current proposed snapshot; never auto-committed. |

## Outputs

| Output | Description |
|---|---|
| `result-state` | NO_BASELINE, UNCHANGED or CHANGED. |
| `change-count` | Number of normalized changes. |
| `baseline-established` | Whether a prior reviewed baseline existed. |
| `report-path` | Generated delta report path. |
| `proposal-path` | Generated current snapshot proposal path. |
| `reason-codes` | Deterministic change reason codes. |

## Permissions, secrets and data

- The Action itself does not require repository write permission.
- No ECZ-ID secret or API key is required for this public Action.
- Supported workflow/configuration files are read locally inside the GitHub Actions workspace; repository source is not uploaded to ECZ-ID.
- The complete first-run example grants only `contents: read`; tighten or extend permissions only when the rest of your workflow genuinely needs more.
- See [PRIVACY.md](./PRIVACY.md), [SECURITY.md](./SECURITY.md) and [SUPPORT.md](./SUPPORT.md) for the complete public boundary.

## Version pinning

The examples use the stable `@v1` compatibility tag. For policies that require an immutable third-party reference, pin this Action to the full commit SHA of the reviewed release. GitHub Actions does not support action-name redirects as a substitute for a stable reference.

## Trust boundary

- Bounded deterministic evidence/current-state processing.
- No hidden telemetry.
- No repository code execution.
- Missing ECZ-ID or missing evidence never means unsafe, non-compliant or untrusted.
- No automatic ownership inference.
- No pay-to-pass.
- No global safety/certification/compliance/approval verdict.
- Local policy decides.

## ECZ-ID identity model

A free Declared Business Passport is the organisation Parent gateway for the seven free machine Passport families: Agent, MCP, Plugin, API, IoT / Device, SDK, and Service & Workload. Verified or Assured strengthens the same Parent ECZ-ID; it does not automatically independently verify a child Passport.

When an identity/currentness next step is warranted, ECZ-ID returns at most one neutral route. Payment never changes the technical result.

[Choose the right free Passport →](https://developers.ecocitizenz.com/get-started/free-passport/?utm_source=github&utm_medium=action-readme&utm_campaign=github-actions&utm_content=eczid-trust-delta&ecz_source=github&ecz_surface=eczid-trust-delta&intent=free-passport)

## Works with GitHub, not against it

ECZ-ID complements GitHub-native controls with persistent identity, accountable operator context, declared authority, current state, change and re-checkable evidence. It does not replace CodeQL, secret scanning, dependency review, workflow dependency lockfiles or artifact attestations.

## Support and security

Use the repository issue tracker only for reproducible product defects that contain no secrets or customer-private evidence. Follow [SECURITY.md](./SECURITY.md) for vulnerability reporting and [SUPPORT.md](./SUPPORT.md) for private/commercial support routes.
