# pit-registry

Package index for the [Olive programming language](https://github.com/olive-language/olive).

## Format

Each package has a file at `{2-char-prefix}/{name}` (e.g., `ht/http`).
The file contains one JSON object per line, with one line per published version:

```json
{"name":"http","vers":"1.0.0","deps":[],"cksum":"blake3hex...","dl":"https://github.com/user/repo/releases/download/http-1.0.0/http.pit.zst","yanked":false}
```

## Fields

| Field | Description |
|-------|-------------|
| `name` | Package name |
| `vers` | Exact version string |
| `deps` | Array of `{"name":"..","req":".."}` |
| `cksum` | BLAKE3 hex digest of the `.pit.zst` archive |
| `dl` | Direct download URL of the `.pit.zst` asset |
| `yanked` | Set to `true` to warn users (version not deleted) |

## Publishing

```sh
pit publish
```

Requires `GITHUB_TOKEN` with `repo` scope. Opens a PR automatically.

## Contributing

PRs are validated by CI before merge. Maintainers review and merge.
