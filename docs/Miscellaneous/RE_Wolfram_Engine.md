---
layout: post
title: Wolfram Engine Setup
permalink: /docs/Miscellaneous/RE_Wolfram_Engine
parent: Resources
nav_order: 5
description: "Notes on using Wolfram Engine with JupyterLab on a Linux research server."
last_modified_date: 2026-09-10
---

# Wolfram Engine Setup

Wolfram Language provides tools for symbolic and numerical computation. This note describes a command-line and JupyterLab workflow for a Linux research server.

The original notes were written for Ubuntu 20.04. The instructions below have been revised against the linked documentation, but have not been retested on a fresh Linux installation.

## Wolfram Engine and licensing

Wolfram Engine runs Wolfram Language computations without the full Mathematica notebook interface. The availability of a free edition does not make the engine open source or authorize every use.

License terms depend on the edition and any institutional agreement. Check the [Wolfram Engine FAQ](https://www.wolfram.com/engine/faq/) before using it for teaching, distributing an application, or deploying a service. A university site license may cover uses that the free development license does not.

## Install and activate Wolfram Engine

Download the Linux installer from the [official Wolfram Engine website](https://www.wolfram.com/engine/) and follow its installation instructions. Check the requirements for the version you download; installer size and required disk space vary.

After installation, start the command-line interface:

```bash
wolframscript
```

Complete activation if prompted, using the Wolfram account associated with your download or license. Confirm that a simple expression evaluates correctly before configuring Jupyter.

## Create a JupyterLab environment

Use a separate Python environment for JupyterLab to keep its dependencies separate from the operating system's Python installation. The following example assumes that Conda is already installed and available in your shell.

Create and activate an environment:

```bash
conda create -n WolframJupyter -c conda-forge python jupyterlab
conda activate WolframJupyter
```

Check that Jupyter is available:

```bash
jupyter --version
```

For alternative installation methods, see the [JupyterLab installation guide](https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html). If the command is not found, first check that the environment is active and JupyterLab is installed there.

## Register the Wolfram Language kernel

Installing JupyterLab does not automatically add a Wolfram Language kernel. Use the official [WolframLanguageForJupyter connector](https://github.com/WolframResearch/WolframLanguageForJupyter) to register it.

With the Conda environment active and `wolframscript` available on your path, run:

```bash
git clone https://github.com/WolframResearch/WolframLanguageForJupyter.git
cd WolframLanguageForJupyter
./configure-jupyter.wls add
jupyter kernelspec list
```

The list should contain a Wolfram Language kernel. Its identifier may vary by version. If registration fails, consult the connector's configuration options:

```bash
./configure-jupyter.wls help
```

## Start JupyterLab

From the directory where you keep your notebooks, run:

```bash
jupyter lab --no-browser --ip=127.0.0.1
```

On a remote server, access this local listener through an SSH tunnel. In a terminal on your own computer, replace `user@server` with your server login:

```bash
ssh -N -L 8888:127.0.0.1:8888 user@server
```

Open the localhost URL printed by Jupyter in your browser, including its authentication token. Adjust the forwarded port if Jupyter starts on a port other than 8888.

Select the Wolfram Language kernel when creating a notebook. As a first check, evaluate:

```mathematica
Integrate[x^2, x]
```

For supported output formats and connector behavior, consult the [connector documentation](https://github.com/WolframResearch/WolframLanguageForJupyter). Jupyter provides a notebook interface, but it does not reproduce every Mathematica front-end feature.

## Working with multiple notebooks

Separate notebooks may start separate kernel processes. If another notebook cannot start its kernel, check existing sessions and the limits of your license. Avoid assuming that the same process limit applies to every Wolfram installation.

For language reference material, see the [Wolfram Documentation Center](https://reference.wolfram.com/language/).



