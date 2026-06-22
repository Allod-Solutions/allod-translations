# allod-translations

Community translation files for [ALLOD](https://allod.solutions) - the self-hosted Secure Web Gateway.

## Structure

```
agent/   - Desktop notification strings (shown by the ALLOD agent)
web/     - Web UI strings (allod.io marketing site and portal)
```

Each directory contains one YAML file per locale, named by the two-letter language code (e.g. `sv.yaml` for Swedish, `de.yaml` for German).

## Contributing a translation

1. Fork this repository
2. Copy `agent/en.yaml` to `agent/<your-locale>.yaml` (e.g. `agent/sv.yaml`)
3. Translate the values - keep the keys exactly as they are
4. Do the same for `web/en.yaml` if you want to cover the web UI too
5. Open a pull request

### Placeholder syntax

Agent strings may contain `{name}` placeholders that are replaced at runtime:

```yaml
notify_git_push_blocked_body: "Push to {remote} was blocked by security policy"
```

Keep all placeholders exactly as-is in your translation.

### Locale codes

Use [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) two-letter codes (`sv`, `de`, `fr`, `es`, `ja`, ...).

## How translations are used

The ALLOD agent detects the OS language at runtime and loads the matching locale file. If no translation exists for the detected language, it falls back to English.

The `web/` strings are used by the allod.solutions marketing site, which picks a locale from the browser's `Accept-Language` header.
