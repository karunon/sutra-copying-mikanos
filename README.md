# sutra-copying-mikanos

## How to Build and Run?

1. env
    ```sh
    source $HOME/osbook/devenv/buildenv.sh
    ```
2. make kernel
    ```sh
    cd /workspaces/sutra-copying-mikanos/mikanos/kernel
    make
    ```
3. build
    ```sh
    cd ~/edk2
    ln -s /workspaces/sutra-copying-mikanos/mikanos/MikanLoaderPkg ./
    source edksetup.sh
    ```
4. written in ~/edk2/Conf/target.txt
    ```txt
    ACTIVE_PLATFORM       = MikanLoaderPkg/MikanLoaderPkg.dsc
    TARGET                = DEBUG
    TARGET_ARCH           = X64
    TOOL_CHAIN_CONF       = Conf/tools_def.txt
    TOOL_CHAIN_TAG        = CLANG38
    BUILD_RULE_CONF = Conf/build_rule.txt
    ```
5. build
    ```sh
    cd $HOME/edk2
    build
    ```
6. run QEMU
    ```sh
    $HOME/osbook/devenv/run_qemu.sh Build/MikanLoaderX64/DEBUG_CLANG38/X64/Loader.efi /workspaces/sutra-copying-mikanos/mikanos/kernel/kernel.elf
    ```
