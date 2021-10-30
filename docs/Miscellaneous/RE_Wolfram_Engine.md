---
layout: post
title: Wolfram Engine on Research Server
permalink: /docs/Miscellaneous/RE_Wolfram_Engine
parent: Miscellaneous
---

English
{: label .label-blue}
Writing
{: .label .label-red}

# Wolfram Language Environment for Personal Server

Mathematica and Wolfram mathematical documents, now, have been essential tools and references for many natural science and engineering fields. Many textbooks and Handbooks are reprinted with changing their notation to wolfram math document style. They provide powerful symbolic calculation routines and grand unified system of various engineering and science field for symbolic and numerical calculation. 

Especially, symbolic calculation is killer application of Mathematica. It can implement real calculation module just same methods of derivative process and operations in papers and books. Not only for researchers but also students, plentiful experiences are possible with Mathematica by follwing equations and derivative process in texts. Machine works such as complicate integral and differential operation are easily solved and graphic tools help them to understand subjects well. 

In this document, it will cover constructing personal research server for symbolic computation with Wolfram Engine.


## Wolfram Engine

Wolfram Inc, opened their core engine [**Wolfram Engine**](https://www.wolfram.com/engine/) of products with free for sofrware developer, students and individual researchers. It does not mean they opened their core engine source as open source, only permitted use of program. For example, software distribution including Wolfram Engine, or generating figures for papers and books are prevented by licenses. The educational activities are also included prevented work. If you want use Wolfram Engine for education, you need to get additional educational license from Wolfram Inc. Personal R&D, prototype program developments and studies are possible with Engine. 

Refer to [official site](https://www.wolfram.com/engine/commercial-options/) for details of use. 

## Jupyter Environment

Mathematica does not only consist of Wolfram Engine. It is combination of Wolfram Engine and other software. One of them is Wolfram Notebook. Wolfram Notebook is not opened with Wolfram Engine. However, they provide connection tool with Jupytr Notebook which can alternate Wolfram Notebook. With [**WolframLanguageForJupyter**](https://github.com/WolframResearch/WolframLanguageForJupyter), Wolfram engine can work on Jupyter as kernel.

For server based system, there is [**Jupyter Lab**](https://jupyter.org/) program. Wolfram Engine nicely fit with Jupyter Lab also.

## Construction

You must prepare server environment you can access with web-browser. You can use GCP, AWS, Azura, Orcle Cloud,  Alibaba cloud or your own local server. All procedure is based on Ubuntu environment at least after [20.04 LTS]((https://releases.ubuntu.com/focal/). 

### install of Wolfram Engine

It requires `avahi-daemon` to install. 

```bash
sudo apt update
sudp apt install avahi-daemon
```

Distribution of Wolfram Engine is shell script form. It needs 1 GB storage for script file. For total installation, at least 50 GB storages are required.

You can directly download Linux version with `wget` command on bash shell.

```bash
$ wget https://account.wolfram.com/download/public/wolfram-engine/desktop/LINUX
```

To execute shell script it need `+x` permission. If you try without adding execution permission you will see next comment.

```bash
$ ls -l
-rw-r--r--  1   USER    GROUP   1121463126  Month   Day Hour:Minute LINUX
$ ./LINUX
-bash: ./LINUX: Permission denied
```

You can add permission with next command.

```bash
$ sudo chmod +x ./LINUX
$ ls -l
-rwxr-xr-x  1   USER    GROUP   1121463126  Month   Day Hour:Minute LINUX
```
Now you can run shell script. x64 version Wolfram engine at least requires more than 50GB size storage for install.

After installation complete, you can use Wolfram language with typing `wolframscript`. If you run `wolframscript` first time, you have to do autherization process with your wolfram account.

### Install Jupyter Lab

Bascially, ubuntu has its own python environment. It is wise that seperate your programming work environment and system. So you have to start install [Anaconda](https://www.anaconda.com/products/individual#Downloads) first. 

```bash
$wget https://repo.anaconda.com/archive/Anaconda3-2021.05-Linux-x86_64.sh
```

Same with Wolfram script add `+x` permission and execute.

```bash
$sudo chmod +x Anaconda3-2021.05-Linux-x86_64.sh
$./Anaconda3-2021.05-Linux-x86_64.sh
```

After installation, relogin shell then you can see `(base)` word is attached to front of shell prompt.

```bash
(base) USER_NAME@USER_COMPUTER:~$
```

This means `base` environment is activated. You can activate and deactivate with `conda` command and environment name.

```bash
(base) $ conda deactivate
$ conda activate base 
(base) $
```

Let environment name "WolframJupyter" then new environment can be initilized as next process

```bash
$ conda create WolframJupyter #normal creation
```

With `-n` option you can constraint version of python and install specific python library during creation.

```bash
$ conda create -n WolframJupyter python=3.8 scipy
```
It is same with

```bash
$ conda create -n WolframJupyter python
$ conda install -n WolframJupyter scipy
```

```bash
$ conda activate WolframJupyter
(WomframJupyter) $
```


See [conda document](https://conda.io/projects/conda/en/latest/index.html) for more information.

```bash
$sudo apt update
$sudo apt upgrade
$sudo apt install python3-pip jupyter-core
```

If you get error message when you run `jupyter lab` then you have to add path of jupyter lab to shell `PATH` variable. 

```bash
$sudo export PATH="$HOME/.local/bin:$PATH" 
```

For permanent use, open `~/.bashrc` file and add next line to end of the file.

```
export PATH="$HOME/.local/bin:$PATH"
```

## Use of Wolfram language on Jupyter

You can run every commands on Mathematica in wolfram languge. For example, you can connect internal wolfram database like Wolfram [ChemicalData](https://reference.wolfram.com/language/ref/ChemicalData.html) or external service like Pubchem, ChemSpidyer on wolfram engine just like in Mathematica. See lists of [supported external services](https://reference.wolfram.com/language/guide/ListingOfSupportedExternalServices.html). Refer [Wolfram Documentation Center](https://reference.wolfram.com/language/) for details of Wolfram Language. Basic introduction is on [fast-introduction](https://www.wolfram.com/language/fast-introduction-for-programmers/ko/).

Be sure that, only one wolfram kernel can be executed on your system. If you run some task with A notebook file and you try to run B notebook file using Wolfram kernel, then B file won't work as you expect.


<!--
This is python api wolfram engine case
However, for images like 3D structure of chemical compound, they exist as specipic formatted data that is not directly represented on Jupyter notebook UI, unlikely, many plot libraries in python such as matplotlib. Their result images consquencsly indicated on notebook outcome. Therefore, if you work >



