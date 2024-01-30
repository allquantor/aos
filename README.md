# aos

Version: 1.7.0.            
Module: `b4j92JzHPvskOxGRQb4656MVIQXOm09SR97TK8RGR-E`

## Requirements

* [NodeJS](https://nodejs.org) version 20+

## Getting Started

```sh
npm i -g https://get_ao.g8way.io && aos
```

> NOTE: after the first time you run `aos` it installs it to your local machine, so the next time you want to run `aos`, just type `aos` + [enter]

## About

aos is a command-line app that connects to your `aos` Process on the ao Permaweb Computer Grid. The ao Computer Grid, is like the internet, but for compute. Each Process on the Grid can receive messages and send messages. This cli will allow you to pass LUA expressions to your Process, and those expressions get evaluated and return output to your system.  

## Documentation

Go to [ao Cookbook](https://cookbook_ao.g8way.io)

## For Developers

The aos console is a command-line application that provides a easy to use DX experience to create Processes (aka Smart Contracts) on the ao Computer.

### Command-line options

You can provide a name for a specific Process, if the Process does not exist aos will spawn the process, then every time you run `aos [name]` it will locate that process and interact with it.

```sh
aos [name]
```

#### Flags

| Name | Description | Required |
| ---- | ---------  | ------- |
| `--cron [Interval]` | The cron flag can only be used when spawning a process, it instructs the Process to generate messages every `Interval`. An Interval can be defined with a [n]-(period) for example: 1-minute, 10-minutes, 5-hours, 10-blocks, etc. | 0-1 |
| `--get-blueprints [dir]` | This command will grab blueprints from the `/blueprints` folder or a folder specified by the user. These blueprints are small lua files that can be applied to your process to automatically give it some functionality. | 0-1 |
| `--tag-name [name]` and `--tag-value [value]` | These flags are also only when aos is spawning a Process. You may add many of these combinations as you would like and they will appear on the Process tags object | 0-n |
| `--load [luaFile]` | The load command allows you to load lua source files from your local directory. | 0-n |

### Commands

When running the console, you can type `dot` commands to instruct the console to perform special instructions.

| Command | Description |
| ------- | ---------- |
| `.editor` | This command opens a simple cli editor that you can type on multiple lines, and then you can type `.done` or `.cancel` to exist editor mode. |
| `.load` | This command allows you to load a lua source file from your local directory |
| `.load-blueprint [name]` | This command will grab a lua file from the blueprints directory and load it into your process. |
| `.exit` | This command will exit you console, but you can also do `Ctrl-C` or `Ctrl-D` |

## CUSTOM CUs and MUs

Use specified MUs and CUs

```sh
export MU_URL=http://66.42.91.25:3005
export CU_URL=http://45.32.213.131:3005

aos
```