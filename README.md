# Bank Security Lock System (8086 Assembly)

This project is an **Employee Login & Security System** implemented in **8086 Assembly language** using the EMU8086 environment.  
It simulates a small-scale **bank security lock mechanism**, ensuring only valid employees with correct credentials can access the system.  
After **3 incorrect password attempts**, the account is locked automatically.

---

## 🚀 Features

 ✔ Employee Authentication
- Accepts and verifies employee IDs.
- Searches the ID inside a 20-employee lookup table.

✔ Password Validation
- Each employee has a stored password (0–15).
- Password is checked based on index mapping.
- After a correct login, user gets an **Access Granted** message.

 ✔ Auto Account Locking
- Allows only **3 wrong attempts**.
- Locks the account after 3 failed tries.

 ✔ Password Update
- After successful login, the user can:
  - Press **Y** to change password  
  - Enter a new password (0–15)
- Password table is updated dynamically.

---

## 📂 Data Used Internally
| `EmpTable` | 20 × WORD | Stores employee ID numbers |
| `PassTable` | 20 × BYTE | Stores passwords |
| `Attempts` | 20 × BYTE | Tracks wrong login count |
| `CurrentIndex` | 1 BYTE | Stores matched employee index |

---

## 🛠 Tools & Technologies

- **8086 Assembly**
- **EMU8086 Emulator**
- DOS interrupts (`int 21h`)
- `emu8086.inc` macro library

---

## ▶ How to Run the Program

Follow these steps to execute the project smoothly:

### 1️⃣ Install **EMU8086**
Download from:  
https://emu8086-microprocessor-emulator.software.informer.com/

### 2️⃣ Keep Required Files Together
Place the following files in the same folder:  
- `BankLockSystem.asm` (your program file)  
- `emu8086.inc` (macro file required by the program)

### 3️⃣ Assemble & Run the Program
1. Open **EMU8086**  
2. Load your `.asm` file  
3. Click **Compile**  
4. Click **Run**  
5. Use the EMU8086 console to test:  
   - Entering employee IDs  
   - Attempting passwords  
   - Testing incorrect attempts  
   - Trying password change option  

You now have a working Bank Security Lock Simulation.

---

## 📘 Example Employee Credentials

| Employee ID | Password |
|-------------|----------|
| 1001        | 4        |
| 1002        | 7        |
| 1003        | 3        |
| 1013        | 9        |
| 2003        | 2        |
| 3005        | 13       |

(You can test all 20 from the table inside the program.)

---

