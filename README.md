# @azu/renovate-config [![Actions Status: test](https://github.com/azu/renovate-config/workflows/test/badge.svg)](https://github.com/azu/renovate-config/actions?query=workflow%3A"test")

[Shareable config](https://renovatebot.com/docs/config-presets/) for [Renovate](https://renovatebot.com)

## Setup

Enable Renovate in your repo and just `extends` in `renovate.json`.

### Default preset

```json5
{
  "extends": ["@azu"]
}
```

Note: Don't necessary to do `npm i -D @azu/renovate-config`

#### Features

- Auto merge patch and major version
- Support Node.js
- It defined packages that require manually updates like TypeScript, Prettier, Linters
- Prevent supply-chain attack by `"stabilityDays": 7`

### Maintenance preset

```json5
{
  "extends": [
    "@azu:maintenance"
  ]
}
```

#### Features

Same features with Default preset.
The only difference from default preset, It does not update major updates.

- Add `{ major: { enabled: false }}`

It aim to less create Pull Request by renovatebot.

## References

- [Renovate Docs](https://renovatebot.com/docs/)
- [Configuration Options \| Renovate Docs](https://renovatebot.com/docs/configuration-options/)
- [Default Presets \| Renovate Docs](https://renovatebot.com/docs/presets-default/)

## License

MIT
