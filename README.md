# Bank Security Lock System (8086 Assembly)

This project is an **Employee Login & Security System** implemented in **8086 Assembly language** using the EMU8086 environment.  
It supports employee authentication, password verification, login attempt tracking, and secure password updates.

The system is designed to simulate a small **bank security lock mechanism**, ensuring that only valid employees with correct credentials can access the system.  
After **3 incorrect attempts**, the account is locked.

---

## 🚀 Features

### ✔ Employee Authentication
- Accepts employee ID numbers
- Searches ID inside a stored employee table (20 employees)
- Validates identity before password prompt

### ✔ Password Validation
- Each employee has a predefined password (0–15)
- Password is matched with the correct employee index
- Up to 3 invalid attempts allowed

### ✔ Auto Account Locking
- After **3 wrong password attempts**, the user is locked out
- Lock persists until program restart

### ✔ Password Update Option
- After successful login, employee can update password
- New password replaces old one in `PassTable`

### ✔ Fully Menu-Driven Text Interface
- Uses DOS interrupts (`int 21h`)
- Works in EMU8086 with `emu8086.inc` macros

---

## 📂 Data Structures Used

| Table | Size | Description |
|-------|------|-------------|
| `EmpTable` | 20× WORD | Stores Employee IDs |
| `PassTable` | 20× BYTE | Stores Employee Passwords |
| `Attempts` | 20× BYTE | Tracks wrong login attempts |
| `CurrentIndex` | 1 BYTE | Stores index during login |

---

## 🛠 Technologies / Tools

- **8086 Assembly Language**
- **EMU8086 IDE**
- `emu8086.inc` (macro file)
- DOS Interrupts (`int 21h`)

---

## ▶ Program Flow

1. Show title  
2. Ask user to enter Employee ID  
3. Search ID in `EmpTable`  
4. If not found → show "ID not found"  
5. If account locked → show "Account locked"  
6. If found → ask for password  
7. Compare with stored password  
8. If wrong → increment attempts  
9. If correct → reset attempts and allow login  
10. Optionally change password  
11. Return to main screen  

---

## 📌 Important Constants

```asm
MAX_EMP EQU 20
MAX_ATTEMPTS EQU 3

▶ How to Run the Program
1️⃣ Install EMU8086

Download from:
https://emu8086-microprocessor-emulator.software.informer.com/

2️⃣ Place emu8086.inc in the same folder as your program.
3️⃣ Assemble & Run

Open the code in EMU8086

Click Compile → Run

Use the console to test employee IDs and passwords
