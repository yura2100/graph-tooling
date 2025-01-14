# The Graph CLI (graph-cli)

[![npm (scoped)](https://img.shields.io/npm/v/@graphprotocol/graph-cli.svg?color=success)](https://www.npmjs.com/package/@graphprotocol/graph-cli)
[![Tests](https://github.com/graphprotocol/graph-cli/actions/workflows/ci.yml/badge.svg)](https://github.com/graphprotocol/graph-cli/actions/workflows/ci.yml)

## The Graph Command Line Interface

As of today, the command line interface supports the following commands:

- `graph init` — Creates a new subgraph project from an example or an existing contract.
- `graph create` — Registers a subgraph name with a Graph Node.
- `graph remove` — Unregisters a subgraph name with a Graph Node.
- `graph codegen` — Generates AssemblyScript types for smart contract ABIs and the subgraph schema.
- `graph build` — Compiles a subgraph to WebAssembly.
- `graph deploy` — Deploys a subgraph to a
  [Graph Node](https://github.com/graphprotocol/graph-node).
- `graph auth` — Stores a [Graph Node](https://github.com/graphprotocol/graph-node) access token in
  the system's keychain.
- `graph local` — Runs tests against a [Graph Node](https://github.com/graphprotocol/graph-node)
  test environment (using Ganache by default).
- `graph test` — Downloads and runs the [Matchstick](https://github.com/LimeChain/matchstick) rust
  binary in order to test a subgraph.
- `graph add` - Adds a new datasource to the yaml file and writes the necessary changes to other
  files - schema.graphql, abi and mapping.

## How It Works

The Graph CLI takes a subgraph manifest (defaults to `subgraph.yaml`) with references to:

- A GraphQL schema,
- Smart contract ABIs, and
- Mappings written in AssemblyScript.

It compiles the mappings to WebAssembly, builds a ready-to-use version of the subgraph saved to IPFS
or a local directory for debugging, and deploys the subgraph to a
[Graph Node](https://github.com/graphprotocol/graph-node).

## Installation

The Graph CLI can be installed with `npm` or `yarn`:

```sh
# NPM
npm install -g @graphprotocol/graph-cli

# Yarn
yarn global add @graphprotocol/graph-cli
```

### On Linux

`libsecret` is used for storing access tokens, so you may need to install it before getting started.
Use one of the following commands depending on your distribution:

- Debian/Ubuntu: `sudo apt-get install libsecret-1-dev`
- Red Hat: `sudo yum install libsecret-devel`
- Arch Linux: `sudo pacman -S libsecret`

## Getting Started

The Graph CLI can be used with a local or self-hosted
[Graph Node](https://github.com/graphprotocol/graph-node) or with the
[Hosted Service](https://thegraph.com/explorer/). To help you get going, there are
[quick start guides](https://thegraph.com/docs/en/developer/quick-start/) available for both.

If you are ready to dive into the details of building a subgraph from scratch, there is a
[detailed walkthrough](https://thegraph.com/docs/en/developer/create-subgraph-hosted/) for that as
well, along with API documentation for the
[AssemblyScript API](https://thegraph.com/docs/en/developer/assemblyscript-api/).

## Releases

The Graph CLI is released on [npm](https://www.npmjs.com/package/@graphprotocol/graph-cli) and
published as a Binary on [GitHub Releases](https://github.com/graphprotocol/graph-tooling/releases).
We support all the version of CLI that support
[Maintenance, LTS and Current Node.js releases](https://github.com/nodejs/Release#release-schedule).
Additionally if there are `graph-node` specific features that are breaking and no-longer supported,
we will drop support for older versions of CLI. After 90 days of a new `Node.js` release, we will
drop support for the oldest `Node.js` version.

End-of-life Releases

| Release    | End-of-life       | Reason                                |
| ---------- | ----------------- | ------------------------------------- |
| `>=0.60.0` | December 31, 2023 | No longer supporting Node 16 or lower |

## License

Copyright &copy; 2018-2019 Graph Protocol, Inc. and contributors.

The Graph CLI is dual-licensed under the [MIT license](LICENSE-MIT) and the
[Apache License, Version 2.0](LICENSE-APACHE).

Unless required by applicable law or agreed to in writing, software distributed under the License is
distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either expressed or
implied. See the License for the specific language governing permissions and limitations under the
License.
