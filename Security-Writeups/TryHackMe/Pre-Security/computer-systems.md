# Computer Systems

## Components

- **Motherboard**: The skeleton and nerves.
- **RAM**: Short-term memory.
- **GPU**: Visual cortex.
- **CPU**: The brain.
- **PSU**: Heart and lungs.
- **HDD + SSD**: Long-term memory.

## Motherboard

- The motherboard holds all the different components in place and connects them to each other.

## CPU

- A CPU does mathematical and logical operations.
- Modern CPUs have multiple cores that handle instructions in parallel.
- The CPU connects to the motherboard through the CPU socket.

## RAM

- RAM holds data that the CPU needs quick access to.
- RAM is volatile: when the power is lost, everything in it is gone.
- Modern RAM uses technologies like DDR4 and DDR5 for higher speed and performance.

## Storage (SSD and HDD)

- HDDs use older technology with moving parts, which limits their speed.
- SSDs have no moving parts and use memory chips, so they're much faster.
- HDDs are still popular because they give large capacity at a low cost.
- Storage connects through SATA cables or PCI Express slots.

## Network Adapter

- A network adapter lets the computer communicate with other systems.
- They come in wireless and wired versions.
- They're often built into the motherboard, but can also be added as expansion cards.
- Network cards usually connect through PCI Express slots.

## PSU

- The PSU (power supply unit) supplies power to all the components.
- It takes power from the wall outlet and shares it out through different connectors, like the main motherboard connector and Molex connectors.
- If the components need more power than the PSU can give, the system will fail.

## Graphics Card

- The graphics card takes information from the operating system and programs, processes it into visuals, and sends them to the monitor.
- Graphics cards connect to PCI Express slots on the motherboard.

## How Does a Computer Start?

**Step 1: Press the power button**
Pressing the power button sends a signal to the PSU to let power flow. It's like our body waking up from sleep: once we get oxygen, our heart starts pumping blood and the body "boots up".

**Step 2: Firmware starts (UEFI/BIOS)**
Now the core components are running, but the "brain" isn't conscious yet. Just like our body, a computer has firmware that gets all its components started. The system that manages this is called **UEFI** (Unified Extensible Firmware Interface).

> Note: You'll often see the term **BIOS** instead of UEFI. BIOS does the same job, but it has mostly been replaced by UEFI.

**Step 3: Power-On Self Test (POST)**
Now it's time to check that everything works properly. If something doesn't, the computer gives warning signals (like beeps). One of the routines UEFI runs is the **Power-On Self Test**, which checks that every required component is present, set up correctly and working.

**Step 4: Select the boot device**
Once everything is working, the system looks for where to start the operating system from. UEFI holds an ordered list (the boot order) of which device to check first for the operating system.

**Step 5: Start the bootloader**
On the chosen boot device, the **bootloader** starts. It loads the operating system from that device into RAM. Once the OS is loaded, UEFI hands control of the components over to the OS.
