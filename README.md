# Managing Kubernetes cluster running on Docker Desktop using Model Context Protocol (MCP)

MCP Server that can connect to a Kubernetes cluster running on Docker Desktop and manage it.


## Prerequisite

- Docker Desktop with Kubernetes enabled
- Install Claude Desktop
- Install Bun on your Macbook

## Install Bun

```
curl -fsSL https://bun.sh/install | bash
```

Ensure that bun CLI is accessible:

```
bun --help
Bun is a fast JavaScript runtime, package manager, bundler, and test runner. (1.2.0+b0c5a7655)

Usage: bun <command> [...flags] [...args]

Commands:
  run       ./my-script.ts       Execute a file with Bun
            lint                 Run a package.json script
  test                           Run unit tests with Bun
  x         eslint               Execute a package binary (CLI), installing if needed (bunx)
  repl                           Start a REPL session with Bun
  exec                           Run a shell script directly with Bun

  install                        Install dependencies for a package.json (bun i)
  add       @shumai/shumai       Add a dependency to package.json (bun a)
  remove    is-array             Remove a dependency from package.json (bun rm)
  update    hono                 Update outdated dependencies
  outdated                       Display latest versions of outdated dependencies
  link      [<package>]          Register or link a local npm package
  unlink                         Unregister a local 
..
...
```

## Install and Run Bun:

Bun is a fast JavaScript runtime, package manager, bundler, and test runner.

The `bun install` command is Bun's equivalent of `npm install` or `yarn install`. 
It manages dependencies for your project.

```
bun install
bun install v1.2.0 (b0c5a765)

+ @types/node@22.10.1
+ shx@0.3.4
+ typescript@5.7.2
+ vitest@2.1.8
+ @kubernetes/client-node@0.20.0
+ @modelcontextprotocol/sdk@1.0.1
+ zod@3.23.8

159 packages installed [2.72s]
```

## Open Claude Desktop

Open Settings > Developer > Edit Config

## Usage with Claude Desktop

```json
{
  "mcpServers": {
    "kubernetes": {
      "command": "npx",
      "args": ["mcp-server-kubernetes"]
    }
  }
}
```

The server will automatically connect to your current kubectl context. Make sure you have:

1. kubectl installed and in your PATH
2. A valid kubeconfig file with contexts configured
3. Access to a Kubernetes cluster configured for kubectl (e.g. minikube, Rancher Desktop, GKE, etc.)



<img width="780" alt="image" src="https://github.com/user-attachments/assets/e2b53e07-e0d8-4030-a5b4-a7bd8cf10616" />


<img width="1166" alt="image" src="https://github.com/user-attachments/assets/d2412bd7-a48a-4820-9513-c029f2edad5b" />


## Accessing Claude Desktop

Open Claude Desktop > Click on "Hammer" sign and see if it detects your Kubernetes configuration.

<img width="904" alt="image" src="https://github.com/user-attachments/assets/19a5bb65-af5f-47ca-810a-5a551c1a76f9" />


<img width="994" alt="image" src="https://github.com/user-attachments/assets/64c44edf-23ed-42f4-8cb6-e9a80ae4c700" />

## List of Kubernetes Available Tools

<img width="602" alt="image" src="https://github.com/user-attachments/assets/e1a92b21-7fe6-4a5d-9da4-72d2d2897ea2" />



## Features

- [x] Connect to a Kubernetes cluster
- [x] List all pods
- [x] List all services
- [x] List all deployments
- [x] Create a pod
- [x] Delete a pod
- [x] List all namespaces
- [ ] Port forward to a pod
- [ ] Get logs from a pod for debugging
- [ ] Choose namespace for next commands (memory)
- [ ] Support Helm for installing charts




