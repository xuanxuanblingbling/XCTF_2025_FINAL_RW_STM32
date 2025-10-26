# XCTF 2025 FINAL RW STM32

- Attachment/RDPbypass.elf: STM32 挑战的 ELF 文件，有调试符号，无正确 M1 UID，用于逆向和调试
- Glitch/power_shorter-1.0.2-py3-none-any.whl: OSR 故障注入设备 PowerShorter 的 python 控制包
- PCB/STM32F103C8T6(White_Button).pdf: STM32F103（白色 Reset 按钮） PCB 的 电路原理图
- STM32CubeProgrammerPatch/STLinkUSBDriver.dll: 使用 Windows 版本的 STM32CubeProgrammer 连接 ST-LINK 时，有可能出现单字节序列号导致无法连接，可以将这个Patch覆盖STM32CubeProgrammer/bin目录下的原始dll，避免出现此现象（在2.16.0版本上测试通过）。

- Attachment/RDPbypass.elf: STM32 challenge ELF，with debug_info, not stripped, no Correct UID, for reverse and debug.
- Glitch/power_shorter-1.0.2-py3-none-any.whl: OSR PowerShorter Control python packages 
- PCB/STM32F103C8T6(White_Button).pdf: STM32F103 Dev Board(White Reset Button) PCB schematic
- STM32CubeProgrammerPatch/STLinkUSBDriver.dll: Using ST-LINK by STM32CubeProgrammer(windows version) may display single-byte serial number, copy this patch to STM32CubeProgrammer to avoid it.(Tested in version 2.16.0)

## Debug

如果使用CVE-2020-15808进行RDP1的绕过，可能需要对目标开发板进行调试，推荐使用OpenOCD。如果需要调试，可以首先关闭STM32F103的RDP1并使用附件中的RDPbypass.elf重新烧写不带正确M1卡UID的固件进行调试。利用成功后，可以让主办方重新刷入原始固件，进行挑战攻击。

Using CVE-2020-15808 to bypass STM32F103 RDP1, you may need to debug the target STM32F103 development board — OpenOCD is recommended. If debugging is required, you can first disable RDP1 on the STM32F103 and reflash RDPbypass.elf(does not contain the correct M1 card). After a successful exploit, ask the organizers to reflash the original firmware so you can carry out the challenge attack.

## Glitch


- [https://gitee.com/osr-tech/powershorter](https://gitee.com/osr-tech/powershorter)

故障注入是一种有概率的，需要运气的攻击手段，如果选手使用故障注入方法完成STM32F103 RDP1绕过，可以向主办方借用OSR PowerShorter，PICO 示波器（数量有限），和容易受故障攻击的STM32开发板（红色RESET按钮）。

Glitch Attack is a probabilistic, luck-dependent attack technique. If participants use Glitch Attack to bypass STM32F103 RDP1 , they can borrow an OSR PowerShorter, PICO oscilloscopes (limited quantities), and Glitch vulnerable STM32 development boards (Red Reset Button) from the organizers.


## NFC

可以向主办方借用NFC读卡器或者PM3。

You can borrow an NFC reader or a PM3 from the organizer.

## Hint

暂无。

None for now.


