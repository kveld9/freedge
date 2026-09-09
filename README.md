# Freedge: minimal and enhanced Microsoft Edge Browser

Keep the Microsoft Edge browser with the minimum, most productive functionalities — reducing resource consumption, eliminating ads, and improving privacy through applied Group Policies.

## Important points

- AI Copilot is enabled.
- Sync account is enabled.

Regarding the two points above: while the overall goal is to strip bloatware, this config was tailored to my own use case. The base setup should still be useful for others — feel free to fork and adjust to your needs.

## Known limitations

- **"Use secure DNS" toggle appears grayed out.** This is expected behavior in Microsoft Edge: as soon as _any_ policy is applied via the registry, Edge treats the browser as "managed" and disables that toggle, regardless of whether `DnsOverHttpsMode` is configured. This isn't something freedge enforces directly — it's a side effect of applying any Group Policy at all, and can't be worked around while using this file.

## How to install?

> Requires running as Administrator (this writes to `HKEY_LOCAL_MACHINE`).

1. Download [freedge.reg](freedge.reg).
2. Double click on the file.
3. Hit "Yes" / "Next" on all the prompts it shows, and it will be applied.
4. Restart Edge for the policies to take effect.

## How to uninstall or revert?

Open Command Prompt **as Administrator** and run:

```dos
reg delete "HKLM\SOFTWARE\Policies\Microsoft\Edge" /f
reg delete "HKCU\SOFTWARE\Policies\Microsoft\Edge" /f
```

Restart Edge afterward for the change to take effect.

Alternatively, keep a backup `.reg` export of your registry state before applying, so you can restore it in one click if needed.

## Linux support

Not supported. I don't recommend Edge for Linux — it ships with far fewer features, and many of these policies aren't available for configuration on that platform. There's no `.reg` (or equivalent) file for Linux in this repo.

## Keeping this updated

The goal is to keep this file current — removing deprecated/obsolete directives and adding new ones as Edge releases them.

- [New policies (release notes)](https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnote-stable-channel)
- [Full policy reference](https://learn.microsoft.com/en-us/deployedge/microsoft-edge-policies)

## Contributing

Found a broken or outdated policy, or want one added/removed? Open an issue or a pull request.

## License

See [LICENSE](LICENSE).
