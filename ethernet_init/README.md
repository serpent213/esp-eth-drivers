# Component for Ethernet Initialization

This component makes it easier to set up and control Ethernet connections in Espressif IoT projects. It hides the lower-level complexities of Ethernet driver initialization and configuration, so developers can focus on building their applications without delving deep into hardware details.
It also allows users to select from various supported Ethernet chips, making development faster.

Supported devices are:

* Internal Ethernet
  PHYs:
    * IP101
    * RTL8201/SR8201
    * LAN87xx
    * DP83848
    * KSZ80xx

* SPI Ethernet
  Controllers:
    * DM9051
    * KSZ8851SNL
    * W5500

* Virtual Ethernet (for emulation, QEMU)
  Drivers:
    * OpenEth

## API

### Steps to use the component in an example code:
1. Add this component to your project using ```idf.py add-dependency``` command.
2. Include ```ethernet_init.h```
3. Call the following functions as required:
    ```c
    // Initialize Ethernet driver
    ESP_ERROR_CHECK(ethernet_init_all(&eth_handles, &eth_port_cnt));

    // Get the device information of the ethernet handle
    eth_dev_info_t eth_info = ethernet_init_get_dev_info(eth_handle);

    // Stop and Deinitialize ethernet
    ethernet_deinit_all(eth_handles);
    ```
