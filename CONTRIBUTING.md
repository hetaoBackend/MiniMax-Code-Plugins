# Contributing

> [!IMPORTANT]
> This repository is archived and no longer maintained. Please fork
> [MiniMax-AI/MiniMax-Code-Plugins](https://github.com/MiniMax-AI/MiniMax-Code-Plugins)
> and submit all new pull requests and issues there.
>
> 本仓库已归档，不再维护。请 Fork 上方的官方仓库，并将新的 Pull Request 和 Issue 提交到那里。

One folder is one Plugin. One pull request is one contribution.

## 1. Create your Plugin

Fork this repository, install dependencies, and run:

```bash
npm install
npm run create -- <github-owner>/<plugin-name>
```

The command creates `plugins/<github-owner>/<plugin-name>` with a portable `plugin.json`, README,
Apache-2.0 license, and starter Skill.

## 2. Make it real

Replace every scaffold `TODO`. Your Plugin must:

- expose at least one Skill or MCP server;
- use the supported package shape in [`docs/plugin-compatibility.md`](docs/plugin-compatibility.md);
- include `README.md`, `LICENSE`, and a matching open-source license in `plugin.json`;
- explain the user problem, an example prompt, and the expected result;
- disclose required executables, accounts, paid services, platforms, network destinations, and data;
- contain no credentials, private endpoints, hidden telemetry, installers, native binaries, or symlinks.

Keep source and docs inside your Plugin directory. Do not edit another contributor's Plugin in the
same pull request.

## 3. Check it

```bash
npm run check
```

The validator checks the hosted directory, Manifest, Skills, MCP transports, required docs,
placeholders, and path safety. CI runs the same command.

## 4. Open the pull request

Include:

- the problem your Plugin solves;
- a copyable example prompt;
- the expected result;
- dependencies and supported platforms;
- network and data behavior;
- automated and manual test evidence.

Review covers usefulness, reproducibility, clear ownership, data flow, dependency risk, and obvious
supply-chain issues. Acceptance means “available as community software”; it is not a MiniMax
endorsement or a complete security audit.

## Update or remove a Plugin

The owner directory identifies the maintainer. Submit changes under the same path and explain user
impact. A Plugin may be quarantined or removed if it becomes malicious, abandoned, misleading, or
unsafe.

## Improve the platform

Validator, documentation, example, and workflow changes are welcome. Open an issue before a
contract-breaking change, add focused tests, and describe migration impact.

Repository contributions are licensed under Apache-2.0. Each hosted Plugin carries its own license.
