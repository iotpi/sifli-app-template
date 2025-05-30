# Workspace Template for porting SiFli to Zephyr RTOS

## Usage

Go to one directory as your root, eg, `$HOME/Dev/Sifli`

### Preparation

```shell
# create a root directory of your workspace
mkdir workspace
cd workspace
```

### Install Python Dependencies and toolchain

    Please refer to official [zephyr document](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) for detailed installation instructions

```shell
python -m venv .venv
. .venv/bin/activate
pip install west
```

```shell
west init -m https://github.com/iotpi/sifli-app-template.git

west update
west zephyr-export
west packages pip --install

# install zephyr sdk if you didn't yet
west sdk install -t arm-zephyr-eabi
```
## Build

```shell
west build -p always -b em-lb525 zephyr/samples/hello_world/
```
