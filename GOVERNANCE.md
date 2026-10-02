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

## Who writes the changes

The owner decides what is published. AI assistants help write the changes, working in the owner's
environment under the owner's review; the `Co-Authored-By` trailer on a commit records which model
wrote it. An assistant does not widen its own permissions or change a repository setting; those are
the owner's.

## Where to report

Corrections, defects and questions go to the issue tracker linked above. A licence request
(commercial use, or distributing an adapted version) goes the same way or through **github.com/HetCreep**
([`CONTRIBUTING.md`](CONTRIBUTING.md)).
