# Ardium
**High-Performance Systems Programming Language with First-Class Native UI**

![Status](https://img.shields.io/badge/Status-Alpha-orange) ![License](https://img.shields.io/badge/License-MIT-blue)

> **"Systems Performance. Pythonic Simplicity. Native UI Integration."**

**Ardium** เป็นภาษาโปรแกรมเชิงระบบ (Systems Programming Language) ชนิด Statically-typed ที่พัฒนาบนโครงสร้างของ **LLVM** ถูกออกแบบมาเพื่อผสานประสิทธิภาพของการจัดการหน่วยความจำระดับต่ำ เข้ากับความสะดวกในการพัฒนาแอปพลิเคชันระดับสูง

จุดเด่นสำคัญของ Ardium คือสถาปัตยกรรมที่กำหนดให้ **GUI เป็น First-class Citizen** ช่วยให้นักพัฒนาสามารถสร้าง Native Application (เริ่มต้นที่ macOS) ได้โดยตรงผ่าน Standard Library ของภาษา โดยไม่จำเป็นต้องพึ่งพา External Bindings หรือ Framework ภายนอก

---

## Technical Overview (ภาพรวมทางเทคนิค)

| Feature | Ardium | C++ | Rust | Python |
| :--- | :--- | :--- | :--- | :--- |
| **Performance** | Native (LLVM) | Native | Native | Interpreted |
| **Memory Management** | RAII / Optional Manual | Manual | Ownership/Borrow Checker | Garbage Collector |
| **Learning Curve** | Moderate | High | Steep | Low |
| **Native GUI Support** | **Built-in (CoreUI)** | 3rd Party Libs | 3rd Party Libs | 3rd Party Libs |
| **Compilation Speed** | Fast | Slow | Slow | N/A |

### Core Features (คุณสมบัติหลัก)

* **Deterministic Memory Management:** บริหารจัดการหน่วยความจำโดยปราศจาก Garbage Collector ใช้หลักการ RAII (`@owned`) เพื่อความปลอดภัยและประสิทธิภาพสูงสุด พร้อมรองรับการจัดการ Pointer แบบ Manual เมื่อจำเป็น
* **LLVM-Based Compilation:** คอมไพล์ Source Code เป็น Machine Code โดยตรงผ่าน **LLVM 19** รองรับการทำ Optimization ระดับสูง
* **Declarative UI Syntax:** ชุดคำสั่งสำหรับการสร้าง Native UI ที่กระชับและอ่านง่าย (เช่น `@VClass`, `@HClass`) โดยทำงานร่วมกับ OS API โดยตรง
* **Seamless C Interoperability:** สามารถเรียกใช้งาน Library และฟังก์ชันภาษา C ได้ทันทีโดยไม่มี Runtime Overhead (Zero-cost FFI)

---

## Usage Example (ตัวอย่างการใช้งาน)

![Ardium GUI Demo](gui.png)

---

## Installation (การติดตั้ง)

ปัจจุบัน Ardium อยู่ในสถานะ Alpha และรองรับการติดตั้งผ่านการ Build จาก Source Code (รองรับ macOS และ Linux):

**Prerequisites:**
* LLVM 19
* CMake
* C++ Compiler (Clang/GCC)

**Build Instructions:**

```bash
# 1. Clone the repository
git clone [https://github.com/SPUAICLUB-OSS/ardium.git](https://github.com/SPUAICLUB-OSS/ardium.git)
cd ardium

# 2. Configure and Build
mkdir build && cd build
cmake ..
make -j$(nproc)

# 3. Install (Optional)
sudo make install
