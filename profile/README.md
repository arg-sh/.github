<h3 align="center">
	<img src="https://raw.githubusercontent.com/arg-sh/argsh/main/argsh.svg" width="48" alt="argsh logo"/>
	<br/>
	arg.sh
</h3>

<p align="center">
  <strong>Make Bash a structured language.</strong>
</p>

<h6 align="center">
  <a href="https://arg.sh/getting-started">Quickstart</a>
  ·
  <a href="https://arg.sh/command-line-parser">CLI Parser</a>
  ·
  <a href="https://arg.sh/libraries/overview">Libraries</a>
  ·
  <a href="https://arg.sh/styleguide">Styleguide</a>
  ·
  <a href="https://arg.sh">Docs</a>
</h6>

<p align="center">
	<a href="https://github.com/arg-sh/argsh/stargazers">
		<img alt="Stargazers" src="https://img.shields.io/github/stars/arg-sh/argsh?style=for-the-badge&logo=starship&color=C9CBFF&logoColor=D9E0EE&labelColor=302D41"></a>
	<a href="https://github.com/arg-sh/argsh/releases/latest">
		<img alt="Releases" src="https://img.shields.io/github/release/arg-sh/argsh.svg?style=for-the-badge&logo=github&color=F2CDCD&logoColor=D9E0EE&labelColor=302D41"/></a>
	<a href="https://github.com/arg-sh/argsh/blob/main/LICENSE">
		<img alt="License" src="https://img.shields.io/static/v1.svg?style=for-the-badge&label=License&message=MIT&logoColor=d9e0ee&colorA=302d41&colorB=b7bdf8"/></a>
</p>

&nbsp;

Bash is powerful and widely available, but easy to write in a way that is hard to read and maintain. **argsh** provides the building blocks to write Bash code that is structured, tested, and production-ready.

&nbsp;

### Highlights

<table>
<tr>
<td width="50%">

**Zero-boilerplate CLI parsing**

```bash
local -a args=(
  'name|n:!'    "Your name"
  'age|a:int'   "Your age"
  'verbose|v:+' "Verbose output"
)
:args "Greet someone" "${@}"
```

Flags, types, defaults, validation, and `--help` — from a plain array.

</td>
<td width="50%">

**Git-style subcommands**

```bash
local -a usage=(
  'deploy|d' "Deploy the app"
  'status|s' "Show status"
)
:usage "App manager" "${@}"
```

Convention-based routing with fuzzy typo suggestions.

</td>
</tr>
<tr>
<td>

**Up to 1500x faster with Rust builtins**

Optional loadable builtins compiled from Rust run natively inside the Bash process — zero fork overhead.

| Flags | Pure Bash | Builtin | Speedup |
|------:|----------:|--------:|--------:|
|    10 |   5405 ms |    4 ms |  1351x  |
|    50 |  29603 ms |   20 ms |  1480x  |

</td>
<td>

**AI-ready out of the box**

```bash
./myscript mcp              # MCP server (stdio)
./myscript docgen llm claude # Anthropic tool schema
./myscript docgen llm openai # OpenAI function calling
```

Every argsh script is an MCP server and LLM tool — no glue code.

</td>
</tr>
</table>

&nbsp;

### Batteries included

| Tool | What it does |
|---|---|
| `argsh test` | Run `.bats` tests with auto-discovery |
| `argsh lint` | shellcheck + argsh-specific checks (AG001–AG013) |
| `argsh coverage` | Coverage reports with minimum threshold |
| `argsh docs` | Generate Markdown, man, RST, YAML from comments |
| `argsh minify` | Bundle + minify + obfuscate into a single script |
| **LSP + Debugger** | Full IDE support — completions, diagnostics, formatting, step-through debugging |
| **Plugin system** | Install, publish, and manage libraries via OCI registries |

Everything runs locally when available, transparently forwards to Docker otherwise.

&nbsp;

### Quick install

```bash
curl -sL https://min.arg.sh > .bin/argsh && chmod +x .bin/argsh
```

Or use the interactive installer:

```bash
bash -c "$(curl -sL https://get.arg.sh)"
```

&nbsp;

### Repositories

| Repo | Description |
|---|---|
| [**argsh**](https://github.com/arg-sh/argsh) | Core framework, builtins, LSP, and tooling |
| [**libs**](https://github.com/arg-sh/libs) | Community plugin libraries (jaml, ...) |

&nbsp;

<p align="center">
  <a href="https://arg.sh">arg.sh</a> · MIT License · Copyright &copy; 2024-present <a href="https://github.com/fentas">Jan Guth</a>
</p>
