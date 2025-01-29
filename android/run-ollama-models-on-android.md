---
icon: brain-circuit
---

# Run Ollama Models on Android

Ollama is a CLI-based tool that allows users to run and manage various AI models locally.

This module is designed for Android users who want to install and run Ollama on their devices using Termux. You need atleast 8GB RAM of android.

By following this guide, you will be able to utilize Ollama's capabilities directly from your Android device.

### Install Termux on Android

Termux is a terminal emulator that enables Android devices to run a Linux environment without requiring root access.&#x20;

It is freely available and can be downloaded from the official [Termux GitHub repository.](https://github.com/termux/termux-app/releases)

### Set Up Termux

You need to set up termux first.

* **Grant storage access**

```
termux-setup-storage
```

This command will access your android storage.

* **Update packages**

```
pkg update && pkg upgrade
```

This will update your packages to new one. Press Y when needed.

* **Install Essential Tools**

```
pkg install git cmake golang
```

These packages provide Git for version control, CMake for software compilation, and Go, the programming language used to develop Ollama.

### Install Ollama

Clone Ollama's Github Repository

```
git clone --depth 1 https://github.com/ollama/ollama.git
```

Navigate to Ollama directory

```
cd ollama
```

Generate Go code

```
go generate ./...
```

Build Ollama

```
go build .
```

After that, start ollama server

```
./ollama serve &
```

Now ollama server will run, you can interact with it.

### Running Ollama models

Now ollama already installed and running, you can run any ollama models.

You can check every [models and library](https://ollama.com/library) on ollama website.

For example, I will use [deepseek-r1 models](https://ollama.com/library/deepseek-r1).

```
./ollama run deepseek-r1:8b
```
