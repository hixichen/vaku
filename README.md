# Vaku

[![Vaku](www/assets/logo-vaku-sm.png?raw=true)](www/assets/logo-vaku-sm.png "Vaku")

[![go.dev reference](https://img.shields.io/badge/go.dev-reference-007d9c?logo=go&logoColor=white&style=flat)](https://pkg.go.dev/github.com/lingrino/vaku/vaku)
[![goreportcard](https://goreportcard.com/badge/github.com/lingrino/vaku)](https://goreportcard.com/report/github.com/lingrino/vaku)
[![codecov](https://codecov.io/gh/lingrino/vaku/branch/master/graph/badge.svg)](https://codecov.io/gh/lingrino/vaku)

Vaku is a CLI and Go API that add useful functions on top of Hashicorp Vault.

## Installation

The easiest way to install the vaku CLI is with [homebrew][]

```console
brew install lingrino/tap/vaku
```

Alternatively, use `go get` to install the latest version of the API and CLI. This command will
install the `vaku` executable and the latest version of the Vault API.

```console
go get -u github.com/lingrino/vaku
```

Next, import vaku in your project like so:

```go
import "github.com/lingrino/vaku/vaku"
```

## CLI

### CLI Summary

The Vaku CLI provides many of the API functions on the command line. You can use it to copy, move,
search, and more on Vault folders or paths. Unlike the Vaku API, the CLI does not provide write or
update commands because of the highly structured data that it expects as input.

### CLI Documentation

Vaku CLI documentation is best read on the command line using either `vaku help [cmd]` or `vaku [cmd] --help`.
Full documentation generated by [cobra](https://github.com/spf13/cobra) is also available in the [docs](docs/vaku.md) folder

```console
$ vaku --help
Vaku CLI extends the official Vault CLI with useful high-level functions

The Vaku CLI is intended to be used side by side with the official Vault CLI,
and only provides functions to extend the existing functionality. Many of the 'vaku path'
functions are very similar (or even less featured) than the vault CLI equivalent. However
vaku works on both v1 and v2 secret mounts, and can even copy/move secrets between them.

Vaku does not log you in to vault or help you with getting a token. Like the CLI,
it will look for a token first at the VAULT_TOKEN env var and then in ~/.vault-token

Built by Sean Lingren <sean@lingrino.com>
CLI documentation is available using 'vaku help [cmd]'
API documentation is available at https://godoc.org/github.com/lingrino/vaku/vaku

Usage:
  vaku [command]

Available Commands:
  folder      Contains all vaku folder functions, does nothing on its own
  help        Help about any command
  path        Contains all vaku path functions, does nothing on its own
  version     Returns the current Vaku CLI and API versions

Flags:
  -o, --format string   The output format to use. One of: "json", "text" (default "json")
  -h, --help            help for vaku

Use "vaku [command] --help" for more information about a command.
```

## API

### API Summary

The Vaku API provides a simple interface for interfacing with both versions of the Vault Key/Value backend. In
addition, the API adds path and folder level functions not fouund in the official vault API such as `FolderCopy()`,
`FolderSearch()`, and `FolderWrite`.

### API Documentation

The API is well documented and can be read on [godoc](https://godoc.org/github.com/lingrino/vaku/vaku). Please use
the godoc documentation for all reference and example information.

TODO - Example

## Contributing

Suggestions and contributions of all kinds are welcome! If there is functionality you would like to see in Vaku
please open an issue or pull request and I will be sure to address it.

TODO - Link to contributing file

## Running Tests

TODO

## TODO

- Benchmarks
- Example functions
- API example in docs
- CLI tests
- Update goreleaser, codecov, golangcilint, badges
- man pages, autocomplete, other cobra features
- how to test version functions?
- www html linting, best practices, css?
- update checkerrors to check every error and require the full error chain in tests
- further parallelize tests?
- update seeds to make more sense maybe?
