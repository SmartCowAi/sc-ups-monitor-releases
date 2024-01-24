# sc-ups-monitor-releases

Repository containing releases of the `sc-ups-monitor` package and its
dependencies for deployment on Jetson devices. Use tags to select the
appropriate version.

## Installation

Use dpkg to first install the dependencies, followed by the `sc-ups-monitor`
package.

For `bionic` devices:

    ```bash
    cd bionic/
    sudo dpkg -i libsystemd0_237-3ubuntu10.57_arm64.deb
    sudo dpkg -i libsystemd-dev_237-3ubuntu10.57_arm64.deb
    sudo dpkg -i sc-ups-monitor_*.deb
    ```

For `focal` devices:

    ```bash
    cd focal/
    sudo dpkg -i libsystemd0_245.4-4ubuntu3.22_arm64.deb
    sudo dpkg -i libsystemd-dev_245.4-4ubuntu3.22_arm64.deb
    sudo dpkg -i sc-ups-monitor_*.deb
    ```

## Notes

`sc-ups-monitor` expexts the UPS' serial port to be accessible at
`/dev/sc_ttyUPS`. Assert that this symlink is present and correctly points to
the UPS' serial port, which is typically `/dev/ttyUSBx` if the UPS is connected
via a USB-serial converter, or `/dev/ttyTHSx` if connected directly to the
Jetson's native serial port.
