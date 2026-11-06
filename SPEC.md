# Lesson 01 specification

## STUDIO-001 · Launch a tested calculator on an existing server

**Status:** Hosted runtime checks, learner browser evidence and the initial
full Linux CI run passed; PR #2 is open and unmerged.
**Next step:** Review the open PR and decide whether to merge; the issue remains
open pending the final GitHub decision.
**Instructor implementation:** [issue #9](https://github.com/kaw393939/373_hosting/issues/9).
Create your own issue from the [lesson template](.github/ISSUE_TEMPLATE/studio-calculator.md).

## Agreed result

Launch the supplied published calculator image through your existing Traefik
network and a nonconflicting HTTPS hostname. Preserve unrelated services and
host access. Do not add another proxy/updater or build a substitute image.
The [release selection](studio/calculator-release.json) supplies the expected
commit and multi-platform digest independently of the running website.
An explicitly agreed adoption of a matching existing deployment is recorded
as adoption, not a fresh launch. This bounded lesson does not certify the whole
server baseline or a vulnerability-free image.

- **Public hostname:** `calc.gerardalmenares.com`; its A record resolved to the selected server address before planning.
- **New launch or adopted deployment, and reason:** New launch explicitly agreed. The initial command started the calculator but failed trusted-HTTPS readiness. The learner then approved a revised resolver plan; the managed calculator was reconfigured and verified. The successful report correctly records `reconfigured` and `new_launch: false`; no successful new-launch report was saved.
- **Own issue / feature branch / PR:** [Issue #1](https://github.com/GerardA8/Gerards-server-studio/issues/1); `studio-001-calculator`; [PR #2](https://github.com/GerardA8/Gerards-server-studio/pull/2).
- **Agreed scope or actual access/configuration gap:** One pinned calculator image on the existing server using verified network `traefik_default`; preserve existing services. After selected labels showed that this route lacked a resolver while existing routes use `le`, the learner approved adding `tls.certresolver=le` to only the calculator route. No proxy settings were changed.

Private SSH targets and configuration stay in ignored local state. Share only
reviewed, selected evidence; never commit credentials or raw server output.

## Evidence to keep

| Evidence | Actual result / link |
|---|---|
| Pre-launch DNS, access, network and route checks | DNS resolves to the selected server address; read-only doctor reported ready on `traefik_default` and `launch-new`. |
| Prepared Black/Pylint/pytest and real-image browser checks | Final Windows `check --fast`: Black passed; Pylint reports POSIX-only `os` members; pytest collection stops because `signal.SIGHUP` is unavailable. E2E not run. Ubuntu CI result pending. |
| Hosted image/commit, trusted HTTPS, valid and rejected API cases | [Sanitized report](studio/evidence.json): approved pinned image/commit, trusted HTTPS, `6 × 7 = 42` (200), division by zero (400), numeric string (422). Provenance is `reconfigured`, not a successful new launch. |
| Preservation of unrelated services | Reconfiguration report checked five unrelated containers' identity, state and published ports; all unchanged. This is a selected check, not a whole-host audit. |
| Own prediction, check interpretation, browser observation and keep/revise reason | [LEARNING.md](LEARNING.md): prediction and check interpretation recorded; learner observed browser/API `42` and chose keep, with reason recorded. |
| Accuracy review before publishing learner excerpts | Learner reviewed and approved the AI-assistance disclosure in [LEARNING.md](LEARNING.md). |
| Actual PR, latest CI, merge and issue closure | [PR #2](https://github.com/GerardA8/Gerards-server-studio/pull/2) is open. [PR checks](https://github.com/GerardA8/Gerards-server-studio/pull/2/checks) links to the latest workflow status; the initial full Linux run passed. Merge and issue closure remain pending. |

Link the exported `studio/evidence.json`, actual CI and issue/PR when available.
CI does not deploy this server. A fixture, green check, timestamp, closed issue
or AI assertion alone does not establish the full result. `status` reports
recorded evidence and readiness for instructor review; it does not grade,
certify authorship or establish understanding.

## Optional instructor history

The records below are background, not steps to repeat. Their original anchors
remain here so earlier links continue to work.

## HOST-001 · Keep the Traefik dashboard private

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-001--keep-the-traefik-dashboard-private).

## HOST-002 · Controlled host maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-002--controlled-host-maintenance).

## HOST-003 · Companion image security maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-003--companion-image-security-maintenance).
