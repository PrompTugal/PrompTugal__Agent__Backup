# Learnings (from the role's history; see history/board/team/backup/debriefs/)

- A shallow clone gives a bundle that verifies but cannot be cloned. Unshallow first, clone the bundle, compare heads, run fsck, run the gate on the restored clone. (6 November, 12:12 UTC)
- A bundle in an ephemeral container is not a backup; only a destination Dinis grants makes it durable.
- A full bundle of the website was about 78 MB; an incremental bundle about 5 MB, so use deltas once a destination exists.
- The Drive tool passes content through the model's context, so it carries manifests only, never the backup.
- Pack vaults: zip only bare/, never local/; restore from a loose zip fails, so test restore on a fresh directory.
- Wave 4 (26 November): the container has no ssh-keygen; apt-get update then install openssh-client. Cloning the website needs a generous timeout (18,000 files).
