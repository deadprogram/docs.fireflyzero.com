---
title: ▶️ Getting started
weight: 5
params:
  art: /hello.png
---

## 👉 Pick the language

Firefly Zero supports lots of programming languages. For simple apps and games, it's a good idea to stick to what you already know. But if you're ready to learn something new for a better results, there are some recommendations:

1. (⌛ Coming soon) [⚡️ Zig](https://ziglang.org/) is simple and gives the best performance but you need to be careful to avoid bugs and memory leaks.
1. [🦀 Rust](https://www.rust-lang.org/) gives performance close to Zig and it's hard to use it wrong, but it's also the most difficult language to learn on the list.
1. [🏃 Go](https://go.dev/) is slower than Rust or Zig but very simple to use and doesn't have memory leaks.
1. (⌛ Coming soon) More languages.

Subjective comparison:

| Language | Simplicity | Performance | Safety  |
| -------- | ---------- | ----------- | --------|
| ⚡️ Zig    | 💻 3/5     | 🐎 5/5      | 🔓 2/5  |
| 🦀 Rust  | 🔬 1/5     | 🐎 5/5      | 🔒 5/5  |
| 🏃 Go    | 🔨 4/5     | 🐇 4/5      | 🔐 4/5  |
| 🐀 C     | 💻 3/5     | 🐎 5/5      | 😕 1/5  |

## 📥 Install tools

1. [Install rust and cargo](https://www.rust-lang.org/tools/install): `curl https://sh.rustup.rs -sSf | sh`
1. Install [firefly-cli](https://github.com/firefly-zero/firefly-cli): `cargo install firefly_cli`
1. [Download emulator binary](https://github.com/firefly-zero/firefly-emulator-bin/releases) and put it into `$PATH`
1. Install [WebAssembly](https://webassembly.org/) compiler for your language:

{{< tabs >}}
{{< tab "Rust" >}}

```bash
rustup target add wasm32-unknown-unknown
```

{{< /tab >}}
{{< tab "Go" >}}

1. [Install Go](https://go.dev/dl/)
1. [Install TinyGo](https://tinygo.org/getting-started/install/)

{{< /tab >}}
{{< tab "C/C++" >}}

The preferred way to build a C (or C++) app is using [wasi-sdk](https://github.com/WebAssembly/wasi-sdk):

1. Go to [wasi-sdk releases](https://github.com/WebAssembly/wasi-sdk/releases).
1. Download and install the latest release for your OS.
1. This should install wasi-sdk into `/opt/wasi-sdk`. If you used an alternative installation method and installed wasi-sdk in a different place, provide the absolute path to it in the `WASI_SDK_PATH` environment variable.

{{< /tab >}}
{{< /tabs >}}

## 💻 Create the project

A new project can be created using `firefly_cli new`:

```bash
firefly_cli new --lang=rust hello-world
```

In this example, it will create `hello-world` directory and initialize in it a Rust-powered app called `hello-world`. Don't think about it too hard, you can later change the project name in the config (`hello-world/firefly.toml`).

## 🏃 Build and run

1. Build and install the app: `firefly_cli build`
1. Run the last built app: `firefly_emulator`

Have troubles using emulator? Check out the [emulator user guide](https://docs.fireflyzero.com/user/emulator/).

## 📦 Distribute

1. Export an app into a zip file: `firefly_cli export`.
1. Publish the file anywhere you like. For open-source projects, a good option is Github Releases.
1. People then can download and install the app:

    ```bash
    firefly_cli import ./joearms.hello-world.zip
    ```

1. Optional: add your app into the catalog: [catalog.fireflyzero.com](https://catalog.fireflyzero.com/).

## 🧠 Further reading

There are several things you should know to make a game:

1. How the runtime works in general. Start by reading about [firefly.toml](https://docs.fireflyzero.com/dev/config/) and then go through all other pages in this documentation in order.
1. What functions the SDK for the programming language that you choose provides:
    1. [🦀 Rust](https://docs.rs/firefly-rust/latest/firefly_rust/)
    1. [🏃 Go](https://pkg.go.dev/github.com/firefly-zero/firefly-go)
    1. [🐀 C](https://github.com/firefly-zero/firefly-c)
1. How to make games and what patterns make it easier. We recommend reading [Game Programming Patterns](http://gameprogrammingpatterns.com/contents.html).
