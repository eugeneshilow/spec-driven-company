# Journal · stacks

## 2026-09-02 15:40 · claude-fable-5 · ⚖️ stacks-as-specs · Stacks are specs in words, not templates

**Decided.** This repository ships no code. A stack is a spec that an agent follows: components, what to build, where to stop, the done criterion. No versions are pinned; the agent installs what is current. The first stack is the one vibecoding.ru runs on.

**Rejected.** A template repository with a working app inside. It would need maintenance with every release of every library, and that maintenance would fall on the author. A spec does not go stale.

**Owner's words.** "We do not want anything but specs in the repo, because then we would have to maintain it all, versions and so on. If we define everything at the level of .md files, it is bulletproof. Let the agents go and install everything themselves."
