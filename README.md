# Hehe

changes #32

# Versioning

Using the [Semantic-Release] tool, we roughly follow [Semantic Versioning] for releases.
Changelog and Releases are automatically generated based on commit messages using the
[Conventional Commits] format.

* A new release is created on each push to `master` which results in at least a `patch`version bump.

* Following types result in the following version bumps:
    * `major`: Triggers a major version bump.
    * `minor`, `feat`: Trigger a minor version bump.
    * `patch`, `fix`, `perf`, `refactor`, `test`, `style`, `revert`, `chore`: Trigger a patch version bump.
    * `docs`, `build`, `ci`: Trigger no version bump (nor release).
    * Moreover, one can use the `BREAKING` footer or `!` before the colon in a commit messages to
      indicate a breaking change and trigger a major version bump.
    * -> For squash merges make sure the commit message header contains the keywords

* Example git log starting with `v1.1.1`, assuming all commits above are pushed at the same time:
    * `ci: migrate CircleCI to GHA` -> no new release
    * `fix: water not flowing` -> `v1.1.2`
    * `patch: water flowing faster` -> `v1.1.2` (increments don't stack for the same release)
    * `feat!: replaced water by lava, adding warmth` -> `v2.0.0`
    * `feat: adds heater` -> `v2.0.0` (superior change already detected previously)

<!--prettier-ignore-start-->

[Semantic-Release]: https://github.com/semantic-release/semantic-release

[Conventional Commits]: https://www.conventionalcommits.org/en/v1.0.0/

[Semantic Versioning]: https://semver.org/

<!--prettier-ignore-end-->