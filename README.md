# presidio-github-task

This repository captures core GitHub collaboration practices across the development-to-production lifecycle.

## GitHub collaboration essentials

### 1. Branching strategy
- Keep `main` stable and production-ready.
- Create short-lived feature branches for each task (`feature/<short-description>`).
- Rebase or merge `main` regularly to reduce conflicts.
- Delete merged branches to keep the repository clean.

### 2. CI checks before merge
- Require automated checks (build, lint, test) on pull requests.
- Block merge when required checks fail.
- Re-run checks after significant updates to a PR.

### 3. Pull request review best practices
- Keep PRs focused and small for faster reviews.
- Provide clear PR descriptions: context, change summary, test evidence.
- Request reviews early and address feedback with follow-up commits.
- Use approval + passing checks as the merge gate.

### 4. Recommended workflow
1. Create a branch from `main`.
2. Commit meaningful, small changes.
3. Open a PR and link related work.
4. Ensure CI passes.
5. Complete code review and approvals.
6. Merge and clean up the branch.

## Project Modules
- **DSA Analytics**: Detailed documentation on developer metric counters and folder traversal recursion in [dsa-docs.md](docs/dsa-docs.md).
- **SQL Schema & Queries**: Relational models, transaction handling, and performance indexing in [sql-docs.md](docs/sql-docs.md).
- **System Design**: Real-time webhook ingestion pipelines, Redis cache deduplication, and database replicas in [system-design-docs.md](docs/system-design-docs.md).
- **SDLC**: Agile Scrum framework, backlog user stories, and weekly reflection notes in [sdlc-docs.md](docs/sdlc-docs.md).
- **CI/CD**: Automation verification workflows, syntax checkers, and branch merge gates in [ci-cd-docs.md](docs/ci-cd-docs.md).

## References
- https://docs.github.com/en/get-started/start-your-journey/hello-world
- https://docs.github.com/en/pull-requests/collaborating-with-pull-requests
- https://dev.to/shubhankarval/github-102-branching-strategies-pull-requests-and-more-11hk
- https://medium.com/javarevisited/git-best-practices-managing-code-repositories-like-a-pro-352f7536c704
