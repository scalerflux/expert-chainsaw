# 🎯 Week 0: Task 1

Basics of digital VLSI SoC Design & Planning

---

## Step 1: Define the goal 🚀  
- Application in C → expected output **O₀**  
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

| Type | What’s inside | When used |
|------|----------------|------------|
| **Microprocessor (MPU)** | CPU core (ALU, control logic, registers, etc.). Needs external memory, I/O, timers. | When you want flexibility, performance, more external components. |
| **Microcontroller (MCU)** | CPU + memory (program & data) + I/O + peripherals (timers, ADC/DAC, etc.), all on one chip. | Embedded tasks, low power, cost/size sensitive. |

---

## Step 4: Physical Implementation & Tape-out 🏗️  
- Floor-planning → placement → clock tree synthesis (CTS) → routing  
- Produce **GDSII** file (fab input)  
- Run checks: **DRC** (Design Rule Check), **LVS** 
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

---


