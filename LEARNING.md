# Lesson 01 · Conversation evidence

AI-drafted task summary, not a transcript or grade. It may be public. Use actual
short quotes or labeled paraphrases, name any help supplied, and link actual
work. Leave missing contributions Pending. A learner can review, correct or
remove excerpts before publication; accuracy approval is not proof of learning.
Label role-play honestly rather than treating it as an actual learner response.

**Lesson:** STUDIO-001. Learner contributions and assistance from this chat
are summarized below.

**Assistance disclosure:** AI helped draft the prediction, check-interpretation
and keep-decision wording; the learner reviewed those explanations. The public
browser observation below is recorded separately as the learner's report.

## Prediction

AI-assisted wording reviewed by the learner: “I expect DNS to point the
hostname to my server’s IP, then Traefik to route the HTTPS request to the
calculator container and return the page to the browser.”

## Check interpretation

AI-assisted wording reviewed by the learner: “It shows that SSH works without
a passphrase prompt and Docker is running. It doesn’t yet prove Traefik
routing, HTTPS, or the calculator works, and the correct Docker network still
needs verification.”

## Browser observation

Learner's separate report about their own public-browser check: they entered
6 × 7; the browser and API both showed 42, which they identified as correct.

## Keep decision

AI-assisted paraphrase reviewed by the learner: they chose to keep the
deployment because the browser and API results both showed 42 for 6 × 7. They
noted that full CI still needs to pass before the assignment is complete.

## Review

Learner confirmed the prediction wording and reviewed deployment plan, which
matches the intended single new calculator deployment while preserving existing
services. After a TLS gap was found, learner approved the narrowly scoped `le`
resolver correction and its revised plan. Accuracy review is not evidence of
understanding.

## AI work and next step

Learner reported interactive SSH succeeded but required the key passphrase;
after the learner added the key to the local SSH agent, non-interactive SSH and
read-only Docker/network and Traefik hostname checks succeeded. DNS for the
chosen hostname later resolved to the server. Studio doctor reported the
existing network ready and `launch-new`; the learner reviewed the pinned-image
plan. Windows `check --fast`: Black passed, Pylint flagged POSIX-only `os`
members, and pytest collection stopped because Windows lacks `signal.SIGHUP`;
E2E was not run. The configured Ubuntu CI result is pending. The initial launch
command started the calculator but stopped because trusted HTTPS did not become
ready. AI found this route lacked a TLS resolver while existing routes used
`le`; after the learner approved the revised plan, the CLI reconfigured only
the managed calculator project. Its report passed trusted HTTPS and valid and
rejected API checks, records `reconfigured` (`new_launch: false`), and found
five unrelated containers unchanged in the selected comparison. The
[sanitized runtime report](studio/evidence.json) was exported. No successful
new-launch report exists. Windows `check --fast` still reports POSIX-only
Pylint symbols and a pytest collection error for `signal.SIGHUP`; E2E was not
run, and Ubuntu CI is pending. Learner's public-browser observation and keep
reason are recorded above. See SPEC, [issue #1](https://github.com/GerardA8/Gerards-server-studio/issues/1)
and sanitized evidence; do not fabricate missing conversation or outcomes.
