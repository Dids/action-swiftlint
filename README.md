# GitHub Action for SwiftLint

This Action executes [SwiftLint](https://github.com/realm/SwiftLint) and generates annotations from SwiftLint Violations by using [GitHub Checks API](https://blog.github.com/2018-05-07-introducing-checks-api/).

## Usage

An example workflow to executing SwiftLint follows:

```hcl
workflow "Execute SwiftLint" {
  on = "push"
  resolves = ["swiftlint"]
}

action "swiftlint" {
  uses = "norio-nomura/action-swiftlint@master"
  secrets = ["GITHUB_TOKEN"]
}
```

## Secrets

- Specifying `GITHUB_TOKEN` to `secrets` is required to using [Check Run APIs](https://developer.github.com/v3/checks/runs/) for generating annotations from SwiftLint Violations.

## Example
[Here](https://github.com/norio-nomura/test-action-swiftlint/pull/1/files#annotation_9749095) is an example that actually works.
![screenshot](screenshot.png)

## Author

Norio Nomura

## License

[MIT](LICENSE)
