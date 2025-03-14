# Zest_Radio_WiFi

Zest_Radio_WiFi board support for Zephyr OS.

## Usage

This board enables the following component:

- [Nordic Semiconductor nRF7002](https://www.nordicsemi.com/Products/nRF7002) Wi-Fi companion IC.

:pushpin: This shield defines:

- the default wifi controller: `zephyr,wifi` to `wlan_zest_radio_wifi_<port>`.

:triangular_ruler: To use this shield:

- Update your device tree by adding the `ZEST_RADIO_WIFI(port)` macro to the `app.overlay` file.\
  Replace `port` with the number of the Zest_Core port to which the shield is connected, e.g.:

  ```c
  ZEST_RADIO_WIFI(1) /* Zest_Radio_WiFi connected to Zest_Core first port */
  ```

- Activate support for the shield by adding `--shield zest_radio_wifi` to the west command.

## Advanced Usage

This shield can be hardware-modified to suit your application.

In that case, use instead the alternate variant of the shield:

- Update your device tree by adding the `ZEST_RADIO_WIFI_ALT(port, nss, bucken, irq, vdden)` macro to the `app.overlay` file, with:
  - `port`: number of the Zest_Core port to which the shield is connected,
  - `nss`: wifi controller SPI Slave Select pin,
  - `bucken`: wifi controller buck enable pin,
  - `irq`: wifi controller IRQ pin,
  - `vdden`: wifi controller VDD enable pin.
- Activate support for the shield by adding `--shield zest_radio_wifi_alt` to the west command.
