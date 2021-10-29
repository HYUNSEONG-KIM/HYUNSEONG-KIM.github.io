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

Mathematica and Wolfram mathematical documents, now, have been essential tools and references for many natural science and engineering fields. Many textbooks and Handbooks are reprinted with changing their notation to wolfram math document style. They provide powerful symbolic calculation routines and grand unified system of various engineering and science field for symbolic and numerical calculation. 

Especially, symbolic calculation is killer application of Mathematica. It can implement real calculation module just same methods of derivative process and operations in papers and books. Not only for researchers but also students, plentiful experiences are possible with Mathematica by follwing equations and derivative process in texts. Machine works such as complicate integral and differential operation are easily solved and graphic tools help them to understand subjects well. 

In this document, it will cover constructing personal research server for symbolic computation with Wolfram Engine.


## Wolfram Engine

Wolfram Inc, opened their core engine [**Wolfram Engine**](https://www.wolfram.com/engine/) of products with free for sofrware developer, students and individual researchers. It does not mean they opened their core engine source as open source, only permitted use of program. For example, software distribution including Wolfram Engine, or generating figures for papers and books are prevented by licenses. The educational activities are also included prevented work. If you want use Wolfram Engine for education, you need to get additional educational license from Wolfram Inc. Personal R&D, prototype program developments and studies are possible with Engine. 

Refer to [official site](https://www.wolfram.com/engine/commercial-options/) for details of use. 

## Jupyter Environment

Mathematica does not only consist of Wolfram Engine. It is combination of Wolfram Engine and other software. One of them is Wolfram Notebook. Wolfram Notebook is not opened with Wolfram Engine. However, they provide connection tool with Jupytr Notebook which can alternate Wolfram Notebook. With **WolframLanguageForJupyter**, Wolfram kernel can work on Jupyter as kernel.

For server based system, there is [**Jupyter Lab**](https://jupyter.org/) program. Wolfram Engine nicely fit with Jupyter Lab also.

## Construct

You must prepare server environment you can access with web-browser. You can use GCP, AWS, Azura, Orcle Cloud,  Alibaba cloud or your own local server. All procedure is based on Ubuntu environment. 

### install of Wolfram Engine

It requires `avahi-daemon` to install. 

```bash
sudo apt update
sudp apt install avahi-daemon
```

Distribution of Wolfram Engine 


