# vivado-docker

Vivado installed into a docker image for CI purposes.

## Build instructions

1. Copy the Vivado installation package `FPGAs_AdaptiveSoCs_Unified_2023.2_1013_2256.tar.gz` to this folder.
3. Potentialy modify the `install_config.txt` to change the install options.
4. Build the image (will take about 30 minutes) passing in a build arg
    ```shell
    docker build --build-arg VIVADO_VERSION=2023.2 --build-arg VIVADO_TAR_FILE=FPGAs_AdaptiveSoCs_Unified_2023.2_1013_2256.tar.gz -t vivado:2023.2 .
    ```

## Running

```shell
docker run -ti --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix vivado:2023.2
```
