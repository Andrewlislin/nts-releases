# NTS public distributions

Distribution artifacts for **市场是对的 / Market Is Right**. The development repository remains private.

## 0.2.1 — CLI integration candidate

This release provides local evidence validation, conditional valuation, cross-process handoff, exact-text checks and deterministic HTML reports. It is an integration candidate, **not an approved WorkBuddy marketplace installation**.

Download the wheel and SHA256SUMS from the [v0.2.1 release](https://github.com/Andrewlislin/nts-releases/releases/tag/v0.2.1).

Requires Python 3.11 or newer and network access to install dependencies. macOS arm64 and Linux aarch64 have been tested with Python 3.13. Windows and WorkBuddy-managed installation are not yet verified.

```sh
python -m pip install --no-input 'https://github.com/Andrewlislin/nts-releases/releases/download/v0.2.1/nts_research-0.2.1-py3-none-any.whl#sha256=3f4b7d343e78aec1679aeaf4989c5c60fed44aa303288bbec95751c94e7c77e2'
nts-research status
nts-research demo
```

Run demo only when a synthetic example is intended. `installed=true` does not imply market-data authorization. No real quotes, credentials or user research are bundled.

Commands: `status`, `schema`, `demo`, `research`, `import-westock`, `replay`, `check`, `export`. Use `nts-research <command> --help` for arguments. `check` requires both canonical packet and report. `export` returns an HTML path for the host's `present_files` tool; the chat model should not rewrite the report.

State is stored in `~/.nts/cli` (override with `NTS_CLI_HOME`). Evidence references expire after 24 hours; exported files remain until the user removes them. Real data requires a separately reviewed `NTS_SOURCE_POLICY` and explicit provider storage permission. The CLI does not fetch market data or inspect other connectors' credentials. Local computation needs no NTS account; `auth`/`unAuth` do not authorize or disconnect a data provider.

This release does not certify a full four-role WorkBuddy workflow or migrate the interactive MCP App. It provides no trading execution, return guarantee, or supplier data license.

Contact: flowit@coaseedge.com
