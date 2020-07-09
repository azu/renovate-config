# @azu/renovate-config [![Actions Status: test](https://github.com/azu/renovate-config/workflows/test/badge.svg)](https://github.com/azu/renovate-config/actions?query=workflow%3A"test")

[Shareable config](https://renovatebot.com/docs/config-presets/) for [Renovate](https://renovatebot.com)

## Setup

Enable Renovate in your repo and just `extends` in `renovate.json`.

```json5
{
  "extends": ["@azu"]
}
```

Note: Don't nessary to do `npm i -D @azu/renovate-config`

## Features

- Auto merge patch and major version
- It defined packages that require manually updates like TypeScript, Prettier, Linters
- Support [dependabot compatibility-score](https://dependabot.com/compatibility-score/)
- Support [Source Graph Search](https://about.sourcegraph.com/)

## References

- [Renovate Docs](https://renovatebot.com/docs/)
- [Configuration Options \| Renovate Docs](https://renovatebot.com/docs/configuration-options/)
- [Default Presets \| Renovate Docs](https://renovatebot.com/docs/presets-default/)

## License

MIT
