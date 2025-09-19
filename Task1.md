# Task 1 - Documentation from Learning Video

## 🎯 Objective
To summarize the concepts learned from the introductory video on **Digital VLSI SoC Design and Planning**.

---

## 📖 Key Learnings

flowchart TD
    subgraph Stage1 [📦 C Modeling (O,1)]
        A1[Spec C Model]
        A2[GCC Output (O,0)]
        A3[Testbench in C]
    end

    subgraph Stage2 [📦 RTL Design (O,2)]
        B1[RTL in Verilog]
        B2[Validation vs C Model]
    end

    subgraph Stage3 [📦 SoC Integration (O,3)]
        C1[Processor]
        C2[Peripherals & IPs]
        C3[GPIOs]
    end

    subgraph Stage4 [📦 Physical Design → GDSII]
        D1[Floorplanning]
        D2[Placement]
        D3[CTS]
        D4[Routing]
    end

    subgraph Stage5 [📦 Tapeout & Fabrication (O,4)]
        E1[DRC & LVS]
        E2[Tape-out → GDSII]
        E3[Tape-in → Fabricated Chip]
    end

    Stage1 --> Stage2 --> Stage3 --> Stage4 --> Stage5


### 1. Chip Modeling
- The process begins with **C models**:
  - **GCC output (O,0)** and **Spec C model (O,1)** are compared.
  - A testbench written in **C language** acts as the application driver.
  - The goal is to ensure that GCC output and Spec C model output are the same.
- Importance:
  - Before building any application/system/chip, it must be modeled in **C language**.
  - Only after validation at C level, we move to **hardware description languages** like Verilog.

---

### 2. Transition to RTL
- Next comparison: **Spec C model (O,1)** vs. **RTL model (O,2)**.
- **0,2** represents the **soft copy of hardware** described in Verilog RTL.
- Validation step: outputs of **Spec C model** and **RTL** must match.

---

### 3. SoC Design Flow
From Verilog RTL, the flow branches into two main parts:

#### a) Processor
- Involves generating **Gate Level Netlist (GLN)** → output of **synthesis**.
- GLN must be **synthesizable**.

#### b) Peripherals / IPs
- Two subdivisions:
  - **Macros synthesizable RTL**
  - **Analog IPs (functional RTL)**

- **PLL (Phase-Locked Loop)** or **clock multipliers** are used to match processor speed internally.

---

### 4. SoC Integration
- Integration includes processor + peripherals + GPIOs.
- The output at this stage is **O,3**.
- Verification: check that **O,2 (RTL)** = **O,3 (SoC Integration)**.

---

### 5. RTL to GDSII (Back-End Flow)
- Steps include:
  - **Floorplanning**
  - **Placement**
  - **CTS (Clock Tree Synthesis)**
  - **Routing**
- This constitutes the **Physical Design process**.

- **Macros & Analog IPs** are **hardened (Hard Macros, HM)**.  
- **Processors** are typically **soft logic**, but in some cases can also be **Hard Macros**.

---

### 6. Tapeout and Fabrication
- After physical design, output is a **GDSII file**.
- Perform:
  - **DRC (Design Rule Check)**
  - **LVS (Layout vs. Schematic)**
- Then, the design is given to the **factory**:
  - **Tape-out** → sending the final GDSII.
  - **Tape-in** → receiving fabricated silicon chips.

- Final chip will work with external peripherals.
- Output of this stage is **O,4**.

---

### 7. Verification of Flow
- At every stage, ensure:  
- If all outputs match, the chip is considered **perfectly working**.

---

### 8. Operating Frequency
- In most cases, we are going to do analysis and validation in the range of:
- **100 MHz to 130 MHz**.

---

## ✅ Outcome
- Learned the **entire SoC design cycle** from **C model → RTL → SoC Integration → GDSII → Tapeout → Fabrication**.  
- Understood the importance of **equivalence checking** between different design stages.  
- Clear understanding of how a concept moves from **software modeling** to an actual **fabricated chip**.

