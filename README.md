# @countinghouse/ch-report

The layer-1 usage report of the countinghouse packs: what was read and what was returned, from the runtime's own records, on the command line and as a standalone MCP tool.

**Status: retired (2026-11-11).** The usage report is the runtime's built-in tool `countinghouse_usage_report`; this code moves into countinghouse `lib/usage/` and this package is not published. Until then this repository is read-only history. Runs on [countinghouse](https://github.com/mchen6/countinghouse)
8.0 or later (unreleased; the release that carries the remote client and
local mode). The layer-1 usage report of the countinghouse client packs: a command and a standalone MCP server over stdio.

Part of the countinghouse client packs. Each package has its own repository; the family's design, plan and acceptance
tests are in [ch-packs](https://github.com/mchen6/ch-packs) (public).

## Development

```
npm ci
npm test
```

Pure JavaScript, no native module. Node 24 or later today (the runtime's
floor); 22.16 once countinghouse's floor shim lands (design). CI runs on
Linux, macOS and Windows.

## Publishing

Releases are published by `.github/workflows/publish.yml` under npm
trusted publishing: a `v<version>` tag on a `main` commit whose
package.json carries that version. No npm token exists anywhere and no 2FA
code is typed for a release. One-time setup on npmjs.com, by the
maintainer: the package's first version is published by hand (`npm publish
--access public`, with 2FA); then **Settings → Trusted publishing → GitHub
Actions** with owner `mchen6`, repository `ch-report`, workflow
`publish.yml`, allowing `npm publish` as well as `npm stage publish`;
then **Settings → Publishing access → Require two-factor authentication
and disallow tokens**. A new trusted-publisher configuration must publish
once within two days or it expires.

## License

Apache-2.0.
