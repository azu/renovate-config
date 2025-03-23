# @azu/renovate-config [![Actions Status: test](https://github.com/azu/renovate-config/workflows/test/badge.svg)](https://github.com/azu/renovate-config/actions?query=workflow%3A"test")

[Shareable config](https://renovatebot.com/docs/config-presets/) for [Renovate](https://renovatebot.com)

## Setup

Enable Renovate in your repo and just `extends` in `renovate.json`.

### Default preset

```json5
{
  "extends": [
    "github>azu/renovate-config"
  ]
}
```

Note: Don't necessary to do `npm i -D @azu/renovate-config`

#### Features

- Auto merge patch and minor version
- Prevent supply-chain attack by `"minimumReleaseAge": 7 days`

#### npm/Node.js

- Defined package groups like TypeScript, Prettier, Linters

#### GitHub Actions

- Pin all action's version by default

The recent tj-actions and reviewdog incidents have caused a real problem that happens if we don't fix versions in GitHub Actions.

- [tj-actions changed-files through 45.0.7 allows remote attackers to discover secrets by reading actions logs. Database](https://github.com/advisories/GHSA-mrrh-fwg8-r2c3)
- [GitHub Action supply chain attack: reviewdog/action-setup | Wiz Blog](https://www.wiz.io/blog/new-github-action-supply-chain-attack-reviewdog-action-setup)

It is difficult to figure out which version should be fixed, so we have settled on the direction of always pinning it.

[pinact](https://github.com/suzuki-shunsuke/pinact) or [pin-github-action](https://github.com/mheap/pin-github-action) helps to pin all action's version.


### Maintenance preset

```json5
{
  "extends": [
    "github>azu/renovate-config:non-major"
  ]
}
```

#### Features

Same features with Default preset.
The only difference from default preset, It disables major updates.

- Add `{ major: { enabled: false }}`

It aims to less create Pull Request by renovate-bot.

## Migration from npm based preset to GitHub based preset

If you used default preset, you can migrate to GitHub based preset by following steps.

```diff
{
  "extends": [
-    "@azu"
+    "github>azu/renovate-config"
  ]
}
```

If you used maintenance preset, you can migrate to GitHub based preset by following steps.

```diff
{
    "extends": [
-        "@azu:maintenance"
+        "github>azu/renovate-config:non-major"
    ]
}
```

## Release Flow

```bash
npm version major
git push --follow-tags
```

## References

- [Renovate Docs](https://renovatebot.com/docs/)
- [Configuration Options \| Renovate Docs](https://renovatebot.com/docs/configuration-options/)
- [Default Presets \| Renovate Docs](https://renovatebot.com/docs/presets-default/)

## License

MIT
