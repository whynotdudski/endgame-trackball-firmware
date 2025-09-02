## Endgame Trackball (firmware)

### Building
1. `git submodule update --init`
2. `cd zmk/` 
3. `west init -l app`
4. `west update`

Now, staying in the `zmk` directory, build either with logs:
```shell
west build -s app -b efogtech_trackball_0 -S studio-rpc-usb-uart -S zmk-usb-logging -- -DZMK_EXTRA_MODULES="$(pwd)/../endgame-trackball-config;$(pwd)/../zmk-pmw3610-driver;$(pwd)/../zmk-pointer-2s-mixer;$(pwd)/../zmk-axis-clamper;$(pwd)/../zmk-input-processor-report-rate-limit" -DCONFIG_ZMK_STUDIO=y -DZMK_CONFIG="$(pwd)/../endgame-trackball-config/config"
```

Or without:
```shell
west build -s app -b efogtech_trackball_0 -S studio-rpc-usb-uart -- -DZMK_EXTRA_MODULES="$(pwd)/../endgame-trackball-config;$(pwd)/../zmk-pmw3610-driver;$(pwd)/../zmk-pointer-2s-mixer;$(pwd)/../zmk-axis-clamper;$(pwd)/../zmk-input-processor-report-rate-limit" -DCONFIG_ZMK_STUDIO=y -DZMK_CONFIG="$(pwd)/../endgame-trackball-config/config"
```

Look for `build/zephyr/zmk.uf2` — it's your firmware.

### How to…

| Feature             | Comment                                                                                                                                                                                                           |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ToDo                | …                                                                                                                                                                                                                 |


### Also see
1. Parent repo: https://github.com/efogtech/endgame-trackball
2. ZMK docs: https://zmk.dev/docs/
3. Zephyr 3.5 docs: https://docs.zephyrproject.org/3.5.0/
