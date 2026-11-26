# Restart: how a new session of cl-6.backup continues

1. Read this folder (agent.json, role.md, now.md, learnings.md, proposal-coverage.md), then history/board/team/backup/ (ROLE.md, plan.md, the latest debrief, sessions/).
2. Read PrompTugal__News__Website CLAUDE.md and board/guidance/README.md ("New from Dinis"), and cl-6.abp's policy for me once it exists.
3. Make a new openssl key (P-256 signing, RSA-4096 encryption), private halves mode 600 in the scratchpad; publish site/keys/cl-6.backup.json alone in its commit, mark the old one superseded; set gpg.format ssh, gpg.ssh.program ssh-keygen (apt-get install -y openssh-client if missing), user.signingkey, commit.gpgsign true.
4. Trailers on every commit: Agent: cl-6.backup@PrompTugal.dinis and Claude-Session: <url>.
5. Update agent.json first, then work. dev only.
