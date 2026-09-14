# How these projects are built

The six Rust products share one contributor policy, one CI layout and one
release process. This page states the rules and the reasons.

## Evidence over assertion

A bug report states what was measured, against which released version.
"Reproduced against 0.4.0" is the standard; "the code looks wrong" is not.
Issues follow one shape: *Today / Why it is worth fixing / Fix / Done when*,
with a reproduction. An issue nobody can reproduce cannot be closed honestly.

## A check must be seen to fail

Every new CI check is broken on purpose once, to prove it can fail, before it
is trusted to pass.

termlens's semver gate is the clearest case. `cargo-semver-checks` infers how
much to check from the version number, so a `0.10 → 0.11` bump reads as a major
release and every check is skipped: a public function can be removed in the
same pull request as the bump and the gate stays green. It also cannot see an
item moved behind a feature flag, because the all-features view never loses it.
The gate therefore forces the release type and checks three feature views, and
it ships with three small model crates that exist only to prove it fails on a
removed item and on a gated one. The two known blind spots are asserted as
blind spots, so a future checker version that closes one fails the self-test
and the workaround gets reviewed instead of kept out of habit.

## Say what you did not do

A pull request lists what it left out and why. A known gap is cheap; a false
claim is expensive. Release notes follow the same rule: anything unverified is
marked unverified.

## Stability has a checker attached

termlens 0.11 is a stability candidate: from it, no promised item changes
incompatibly before 1.0. Every sentence of the promise names the CI job or test
that enforces it, or states that nothing does. One such gap is recorded:
`cargo-semver-checks` does not report a method whose type changed under the same
name.

1.0 has no date. It requires an external pilot on a published release candidate,
an observation window counted from that pilot's first green run, every
maintained consumer on the candidate from crates.io, and a daily fresh-install
check that stays green.

## Releases

Releases publish through crates.io Trusted Publishing with short-lived OIDC
tokens; no repository stores a registry token. Tags are protected by a ruleset,
a release re-runs the full CI gates, and the published crate is then verified
from outside: a new consumer project installs it from the registry and drives a
real PTY with it.

## AI tooling

These projects are built with AI assistance, and each CONTRIBUTING says so. I
review, test and maintain the results and I am the author of record.

No commit carries a model's name: no `Co-Authored-By` naming an assistant, no
"Generated with" footer, no bot as author. The Developer Certificate of Origin
is a statement a person makes about code they submit; a tool cannot make it. CI
checks every commit in every pull request for this.
