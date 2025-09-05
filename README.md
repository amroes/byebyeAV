# ByeByeAV.exe - Advanced Antivirus Evasion Tool

A n Advanced antivirus evasion tool that uses process hollowing on dllhost.exe and XOR encryption to bypass detection. Bypassed Latest versions of Kaspersky, Sophos and Windows Defender.

## How It Works

1. **Process Hollowing**: Creates a suspended `dllhost.exe` process
2. **Shellcode Injection**: Injects encrypted shellcode into the process
3. **XOR Encryption**: Bypasses static signature detection
4. **Memory Permissions**: Sets RX permissions for execution

## Quick Setup

### Prerequisites
- Windows 10/11
- .NET Framework 4.7.2+
- Administrative privileges

### Build
```bash
dotnet build --configuration Release
```

## Usage

### Basic Usage
```bash
ByeByeAV.exe
```

### Custom Shellcode
1. **Encrypt your shellcode** using the provided `xor.py` script by replacing shellcode with HTTPS meterpreter shellcode in csharp format and then run :
   ```bash
   python xor.py
   ```

2. **Replace the shellcode** in the source code:
   ```csharp
   byte[] buf = new byte[YOUR_SIZE] {
       // Paste your encrypted bytes here
   };
   ```

3. **Recompile** the project:
   ```bash
   dotnet build --configuration Release
   ```

## XOR Encryption Script

The `xor.py` script makes it easy to encrypt/decrypt shellcode:

## Supported Targets
- Windows Defender
- Sophos Antivirus
- Kaspersky Antivirus

## Security Notice

⚠️ **EDUCATIONAL USE ONLY**

This tool is for defensive research and academic purposes only. Use responsibly and only on systems you own or have permission to test.
