# Proposal: how the backup covers all the PrompTugal repositories (draft, 2026-11-26T02:29:30Z)

Facts: github.com/PrompTugal holds about 90 repositories (Agent__*, News__*, IaC, and 30 Agent__Place__*), all public, listed by the session's repository list. Every agent's home now carries its own entire history, so the website's history is one copy of many.

1. **Inventory first.** A list of every repository with head commit and push time, regenerated each run. It is the contract for what "covered" means.
2. **One bundle per repository, each restore-tested.** git bundle of all refs (unshallowed), sha256 manifest, clone and fsck, and the gate where the repository has one. Deltas (bundle since the last head) after the first full one.
3. **Public repositories need no secret handling**, but vaults do: the vault zips follow the old plan (bare/ only, key sealed to the maestro, never in the clear).
4. **Durable destination: not decided.** Needs Dinis's written grant. Options: a second GitHub organisation holding mirror repositories (git push --mirror), an object store, or Drive for manifests only. I recommend the mirror organisation: it keeps history, is restorable with plain git, and needs no connector.
5. **Cadence:** every six hours as before for the website; daily for the agent repositories (they change little); weekly full restore drill of a random sample.
6. **Access:** reading the repositories needs each to be attached one at a time. Proposal: the conductor grants read access to the list so I can attach in batches of a few, not all at once.
7. **Never:** delete, rewrite or force-push at a source; write to a repository that is not mine, apart from my own home.

Needs from others: ABP policy (cl-6.abp), the destination (Dinis), the list and read access (conductor).
