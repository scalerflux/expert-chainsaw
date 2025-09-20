# 🎯 Week 0 of RISC-V Chip Tapeout program 
<details>
   <summary>Task 1: Video summary</summary>     
   
## Step 1: Define the goal 🚀  
- Application in C → compile →  expected output **O₀**  
- Build a high-level C spec of the processor (not Verilog)  
- Compile the app on spec (e.g. RISC-V GCC / ARM GCC / x86 GCC) → output **O₁**  
- If **O₀ = O₁**, freeze the specification  

---

## Step 2: RTL implementation 🔧  
- Write synthesizable RTL (Verilog), making sure everything is convertible to gates  
- Run same application → output **O₂**  
- Check **O₁ = O₂**  

---

## Step 3: SoC integration ⚙️  
- Separate processor and peripherals in Verilog  
  - **Macros**: repeatable digital blocks  
  - **Analog IPs**: e.g. ADC/DAC for converting analog signals → digital  
- Integrate periph + GPIO etc, run application → output **O₃**  
- Check **O₁ = O₂ = O₃**

---

## Microprocessor vs Microcontroller 🧠  

| Type | What’s inside | 
|------|----------------|
| **Microprocessor (MPU)** | CPU core (ALU, control logic, registers, etc.). Needs external memory, I/O, timers.
| **Microcontroller (MCU)** | CPU + memory (program & data) + I/O + peripherals (timers, ADC/DAC, etc.), all on one chip.

---

## Step 4: Physical Implementation & Tape-out 🏗️  
- Floor-planning → placement → clock tree synthesis (CTS) → routing  
- Produce **GDSII** file (fab input)  
- Run checks: **DRC** (Design Rule Check), **LVS** (Layout vs Schematic)
- **Tape-out**: send to fab  

---

## Step 5: Bring-up & Final Verification 🔍  
- Receive silicon (“tape-in”) → build board with memory, peripherals etc.  
- Load software (via USB or appropriate interface), run the target application → output **O₄**  
- Verify **O₁ = O₂ = O₃ = O₄**  

---

## ✅ Success & Next Steps  
When all outputs are equal, the design is verified: the chip can run the application correctly.  
Then: consider productization, identifying market fit, deployment paths, etc.

</details>

<details>

<summary>Task 2: Tools installation </summary>

## Yosys
```
$ git clone https://github.com/YosysHQ/yosys.git
$ cd yosys
$ sudo apt install make (If make is not installed please install it)
$ sudo apt-get install build-essential clang bison flex \
libreadline-dev gawk tcl-dev libffi-dev git \
graphviz xdot pkg-config python3 libboost-system-dev \
libboost-python-dev libboost-filesystem-dev zlib1g-dev
$ make config-gcc
$ make
$ sudo make install
```
<img width="804" height="627" alt="Screenshot 2025-09-19 at 5 21 06 PM" src="https://github.com/user-attachments/assets/22e4110a-4e47-4dc9-88f0-f3df4294b3a6" />

## Iverilog
```
$ sudo apt-get install iverilog
```
<img width="802" height="639" alt="Screenshot 2025-09-19 at 5 25 18 PM" src="https://github.com/user-attachments/assets/c382d0ee-baa0-44c4-8a91-9e3674be777a" />

## GTKWave
```
$ sudo apt install gtkwave

```
<img width="1000" height="900" alt="Screenshot 2025-09-19 at 5 30 42 PM" src="https://github.com/user-attachments/assets/4a28f5b7-5f0c-4845-ba99-7b8f8b72b6fb" />
<details>

