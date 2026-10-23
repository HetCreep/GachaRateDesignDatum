# GOVERNANCE.md—who decides, and how a change is accepted

## Who decides

**The copyright holder, one person (HetCreep).** There is no committee, no maintainer group and no
vote. The owner has the final word on what is merged, published and retired.

## How a change is accepted

1. **A sourced issue.** Anyone may open an issue at
   https://github.com/HetCreep/GachaRateDesignDatum/issues with the location, the source and the
   wording found there. A proposal with no source cannot be accepted. See
   [`CONTRIBUTING.md`](CONTRIBUTING.md).
2. **The owner rules.** The owner accepts, rejects or holds it.
3. **The change is recorded.** An accepted change gets a version and an entry in
   [`CHANGELOG.md`](CHANGELOG.md). A released entry is not edited after the fact; a correction gets
   a new entry.

The rules for changing a value in the document itself (who ratifies a BASE value, adversarial
review, how a source-backed value is revalidated) are in the published page `docs/governance.md`.
This file does not restate them.

## How a version is sized

Versions follow [Semantic Versioning](https://semver.org/). The size of an entry is decided by what
it does to a design that already conforms:

- **PATCH:** wording, citations, an exemplar note, or a correction that moves no BASE value and no
  invariant and adds nothing normative (v1.1.3, v1.1.4, v1.2.1 and v1.2.2 were sized so).
- **MINOR:** a new normative rule or invariant, or a new option. Nothing an existing design already
  does becomes wrong, though a new rule can need new work before the design conforms again (v1.1.0
  added I19; v1.2.0, multi-level pity).
- **MAJOR:** a locked rule changes meaning or a BASE value moves. Something a conforming design
  already does may become wrong.

## Who writes the changes

The owner decides what is published. AI assistants help write the changes, working in the owner's
environment under the owner's review; the `Co-Authored-By` trailer on a commit records which model
wrote it. An assistant does not widen its own permissions or change a repository setting; those are
the owner's.

## The documentation site

The documentation site is a reading copy, published from this repository by the platform's sync. **The
site is not a write surface:** no change to the document or to any page of this repository is made through the site's editor. A commit
on the default branch whose subject starts with `GITBOOK-` would mean that rule failed, and the
`check` workflow fails the push that carries one.

## Where to report

Corrections, defects and questions go to the issue tracker linked above. A licence request
(commercial use, or distributing an adapted version) goes the same way or through **github.com/HetCreep**
([`CONTRIBUTING.md`](CONTRIBUTING.md)).
