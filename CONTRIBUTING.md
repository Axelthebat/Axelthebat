# Contributing

Thanks for helping. This is a small, mostly personal project space, so the process is light. A few conventions go a long way.

## Where things go

| You want to | Use |
|---|---|
| Report a bug | **Issues**, with the [bug report template](.github/ISSUE_TEMPLATE/bug_report.md) |
| Propose a feature or a design | **Discussions**, category [Ideas](https://github.com/Axelthebat/Axelthebat/discussions/new?category=ideas) |
| Ask a question | **Discussions**, category [Q&A](https://github.com/Axelthebat/Axelthebat/discussions/new?category=q-a) |
| Share your work | **Discussions**, category [Show and tell](https://github.com/Axelthebat/Axelthebat/discussions/new?category=show-and-tell) |
| Report a vulnerability | The [security policy](SECURITY.md), privately. Do not open a public issue. |

The rule of thumb: if it needs a decision or an explanation, it is a discussion. If it needs a fix, it is an issue.

## Pull requests

1. Open an issue or a discussion first for anything larger than a typo. It saves everyone time.
2. Keep one concern per pull request. Small, focused diffs get reviewed.
3. Use conventional commit messages:

   ```
   feat: add --format json output
   fix: panic when the config file is empty
   docs: clarify the SECURITY.md reporting steps
   chore: bump dependencies
   ```

4. Run the checks before pushing. For Rust: `cargo fmt`, `cargo clippy`, `cargo test`. For Go: `go vet`, `golangci-lint`, `go test ./...`. For Python: `ruff`, `mypy`, `pytest`. CI runs the same commands, so a red local run means a red CI run.
5. Add a test with every bug fix. A regression test is the cheapest proof that the fix holds.
6. Update the documentation in the same pull request. A behaviour change without a README update is an incomplete change.

## Security

Do not open a public issue, discussion, or pull request for a vulnerability. Follow [SECURITY.md](SECURITY.md) and report it privately. Include the affected version, steps to reproduce, and impact.

## Commit signing

Signed commits are appreciated but not required. If you have a GPG or SSH key configured, GitHub shows the verified badge, which helps me trust patches from unfamiliar contributors.

## Code of Conduct

Participation is governed by the [Code of Conduct](CODE_OF_CONDUCT.md). It applies to every space here, including Discussions.

## License

By contributing, you agree that your contributions are licensed under the [MIT License](LICENSE).
