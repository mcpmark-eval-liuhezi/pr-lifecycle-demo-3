# PR Lifecycle Demo — Run Log

> **Where this log lives:** It was intended for a secret gist, but gist creation is blocked by the
> current API token (403, "Resource not accessible by personal access token"). It is committed to
> this branch (`demo-log`) in the demo repository instead, keeping the log off the default branch
> and out of the pull request's change set.

Sandbox repository: **pr-lifecycle-demo-3** (https://github.com/mcpmark-eval-liuhezi/pr-lifecycle-demo-3)
Feature branch: **feature/greeting-tweak**
Pull request: **#1** — "Demo: update greeting text" (https://github.com/mcpmark-eval-liuhezi/pr-lifecycle-demo-3/pull/1)
Default branch: **main**

## Numbered log of the run

1. Identified the demo GitHub account: **HeziLiu**.
2. Attempted to create the sandbox repository `pr-lifecycle-demo` under the personal account — blocked by the API (403, "Resource not accessible by personal access token"). Verified this was a token-permission block, not a name collision: the name was free on the personal account.
3. Fell back to the one organization the account belongs to (`mcpmark-eval-liuhezi`). `pr-lifecycle-demo` was already taken there, and so was `pr-lifecycle-demo-2`, so per the fallback rule the sandbox was created as **pr-lifecycle-demo-3** (public).
4. On the default branch `main` (auto-initialized), wrote two files in a single commit: a `README.md` explaining this is a pull-request lifecycle demo sandbox, and a small Python script `greeter.py` that prints `Hello, world!`.
5. Created the feature branch **feature/greeting-tweak** off `main`.
6. On `feature/greeting-tweak`, changed the greeting in `greeter.py` to something friendlier: `Hello there, friend — great to see you! 🎉` (commit `1fbc469`).
7. Verified before moving on: read `greeter.py` back from `feature/greeting-tweak` and confirmed the friendlier greeting had actually landed on that branch (and that `main` still had the original).
8. Opened a **draft pull request**: #1, titled "Demo: update greeting text", from `feature/greeting-tweak` into `main`.
9. Inspected the pull request's own change set before taking it out of draft: exactly one file, `greeter.py` (+1/−1, modified). No other files.
10. Because `greeter.py` was the only file in the change set, flipped the pull request to **ready for review** and updated its description to include a one-line summary of the change.
11. Confirmed afterwards: the pull request now shows as **open and ready for review** (state `open`, `draft: false`), with 1 commit, 1 changed file, +1/−1, and it is mergeable (clean).
12. Review status at time of logging: **no reviews yet** (no submitted reviews).
13. Status checks at time of logging: **none yet** (no CI workflows configured; 0 checks reported).
14. Org teams: the account belongs to org `mcpmark-eval-liuhezi` but to **no teams**, so there are no team rosters to draw invitees from.
15. For reproducibility — the latest release of the official `github/github-mcp-server` project, looked up live at run time (not from memory): tag **v2.0.3** ("GitHub MCP Server 2.0.3", https://github.com/github/github-mcp-server/releases/tag/v2.0.3).

## Notes / caveats

- The repository lives under the org `mcpmark-eval-liuhezi` rather than the personal account, because the API token in use cannot create repositories on the personal account (403). If the personal account is preferred, a token with repo-creation scope on `HeziLiu` is needed.
- The name ended up as `pr-lifecycle-demo-3` because both `pr-lifecycle-demo` and `pr-lifecycle-demo-2` already existed in that org.
- The gist could not be created for the same token reason (403 on gists); this file on the `demo-log` branch is the substitute. With a fuller token it can be copied into a secret gist verbatim.
- No other blockers: branch, commits, draft PR, change-set check, ready-for-review flip, and description update all completed cleanly.
