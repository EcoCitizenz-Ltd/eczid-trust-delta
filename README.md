# ECZ-ID Trust Delta

Compare normalized GitHub workflow authority/currentness evidence with a reviewed baseline without retaining raw source or secret names.

## Outcome

Answer what changed since a reviewed workflow/Agentic authority baseline without pretending no-baseline means unchanged.

## Quick start

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

## Works with GitHub, not against it

ECZ-ID complements GitHub-native controls with persistent identity, accountable operator context, declared authority, current state, change and re-checkable evidence. It does not replace CodeQL, secret scanning, dependency review, workflow dependency lockfiles or artifact attestations.

## Support and security

Use the repository issue tracker only for reproducible product defects that contain no secrets or customer-private evidence. Follow [SECURITY.md](./SECURITY.md) for vulnerability reporting and [SUPPORT.md](./SUPPORT.md) for private/commercial support routes.
