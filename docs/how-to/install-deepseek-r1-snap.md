(install-deepseek-r1-snap)=
# Install Deepseek R1 snap

The Deepseek R1 snap installs a hardware-optimized runtime for inference with the Deepseek R1 LLM.
It supports a range of hardware, in many cases with the help of drivers installed on the host.

This snap works with amd64 and arm64 CPU architectures and has been tested on Intel, AMD, and Ampere CPUs.
It is also compatible with Intel and Nvidia GPUs, as well as Intel NPUs.

```{note}
    This snap has mainly been tested on Ubuntu 24.04 and newer systems.
    For the best experience, make sure the drivers are installed on the host 
    before installing the snap.
```
## Installation

Open a terminal.
Set the right channel and install the model snap by executing:

```bash
    sudo snap install deepseek-r1 --channel=<channel>
```

During installation, the snap detects the hardware and picks a suitable stack.

## Using the snap
Two use cases have currently been tested for the Deepseek R1 snap.
You can run a server on the snap or use it with a chat client to prompt the LLM.

### Run server

Each stack that is installed consists of an inference engine and a model.
The inference engine is a server application.

To start the server:

```bash
    sudo snap start deepseek-r1
```

When the server is running, it exposes an an [OpenAI compatible endpoint](https://github.com/openai/openai-openapi) served via HTTP. 
The HTTP server's bind host and port have the following default values:

```{terminal} 
:input: sudo snap get deepseek-r1 http

Key        Value
http.host  127.0.0.1
http.port  8080
```

To change, for example, the HTTP port to 8999:

```bash
    sudo snap set deepseek-r1 http.port=8999
```

Once changed, restart the server:

```bash
    sudo snap restart deepseek-r1
```
Check out the configuration page for details on config options.

To debug possible issues, you can query the server logs:

```bash
    sudo snap logs deepseek-r1
```
To query more lines and follow the logs, use `-n -100 -f`.

### Chat with Deepseek R1

You can use a range of OpenAI-compatible chat clients to interact with the server.
The snap also ships an application that allows basic prompting from the command line.

To run the built-in chat application:

```bash
    deepseek-r1.chat
```
