# my-mcp-server

Learning MCP: tiny notes server with five tools

Side project, maintained when I have time.

## Examples

```bash
# claude_desktop_config.json  (use ABSOLUTE paths: Claude does not
# run from the repo directory, so a bare "server.py" is not found)
# {
#   "mcpServers": {
#     "notes-box": {
#       "command": "python",
#       "args": ["/abs/path/to/my-mcp-server/server.py"],
#       "env": {"MCP_NOTES_FILE": "/abs/path/to/notes.json"}
#     }
#   }
# }
python server.py --help
```

## Highlights

- Atomic saves (temp file + os.replace) behind a write lock
- Notes path set by MCP_NOTES_FILE or --notes-file
- Five tools: add / get / update / delete / list notes
- Includes a Claude Desktop config snippet with absolute paths
- A missing note raises instead of returning the string 'not found'
- Every tool carries a real docstring, so clients get descriptions

## Installation

```bash
pip install -r requirements.txt
```

## Project structure

```text
├── docs/
│   ├── development.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── tests/
│   └── test_notes.py
├── .gitignore
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
├── requirements.txt
└── server.py
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## Changelog

- `0.1.1` - fix edge case in argument parsing
- `0.1.0` - first working version
