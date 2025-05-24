# USRP JTAG Flash

Sometimes, we break things...
In case the FPGA image of USRP is corrupted and the URSP is not responding,
this script allows flashing an image to recover it, without needing the Xilinx GUI.

Xilinx Vivado is still a requirement to flash the device.

Original source is the [UHD repo](https://github.com/EttusResearch/uhd),
They come from the `FPGA/usrp3` part, so may only work with USRP3 devices.
They are probably licensed under LGPLv3.
[Upstream steps for X310](https://files.ettus.com/manual/page_usrp_x3x0.html#x3x0_load_fpga_imgs_jtag).

## How to

1. Modify the `VIVADO_EXEC` in `viv_jtag_program` to point to the Xilinx Vivado binary.
2. Connect your PC to the JTAG interface.
3. Run `./viv_jtag_program [bit/bin FPGA image]`.

After this, you should be able to communicate with the USRP again.
You also should load a valid FPGA image with the `uhd_image_loader`,
images flashed with the JTAG are volatile.
