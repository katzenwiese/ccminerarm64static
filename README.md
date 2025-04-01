# ccminer (Statically Linked ARM64 Binary)

This repository provides a statically linked `ccminer` ARM64 binary that can be used directly on any ARM64 device without requiring additional libraries or building from source. The binary is completely self-contained and does not rely on dynamic linking.

## Features
- ✅ Statically linked: No external libraries or dependencies required.
- ✅ Compatible with all ARM64 devices (e.g., Android devices, SBCs).
- ✅ Ready to be pushed and executed on ADB-connected devices.
- ✅ Built with musl and statically linked OpenSSL.

## Usage

### Example Command
```
ccminer -a verus -o stratum+tcp://162.55.8.164:9998 -u RKXRZc2ChszCToRpQNaR5fXLrzGccGyHZa.arm64 -p x -t 8
Note : The IP in the command is a PUBLIC Mining Pool part of an example command, do not use for illicit purposes as they will blacklist you, only use it for and on devices you own and have permission to mine on.
URLs do NOT work, you need to use the stratum ip directly (just ping the stratum url to get it)
```

**Flags:**
- `-a verus` : Algorithm to use (in this case, VerusHash).
- `-o stratum+tcp://162.55.8.164:9998` : Pool URL and port for mining.
- `-u RKXRZc2ChszCToRpQNaR5fXLrzGccGyHZa.arm64` : Wallet address and worker name.
- `-p x` : Password (can be left as `x` if not required by the pool).
- `-t 8` : Number of threads to use.

### Direct Execution (Linux/Unix ARM64 Device)
1. Download the binary.
2. Grant execution permission:
   ```bash
   chmod +x ccminer
   ```
3. Run `ccminer`:
   ```bash
   ./ccminer -o <pool_url> -u <username> -p <password>
   ```

### Pushing to ADB Device (Android)
1. Connect your ARM64 device via ADB.
2. Push the binary to the device:
   ```bash
   adb push ccminer /data/local/tmp/
   ```
3. Grant execution permission:
   ```bash
   adb shell chmod +x /data/local/tmp/ccminer
   ```
4. Run `ccminer` on the device:
   ```bash
   adb shell /data/local/tmp/ccminer -o <pool_url> -u <username> -p <password>
   ```

## Requirements
- ARM64 architecture device.
- ADB installed (if using on Android devices).

## Notes
- Ensure your binary is named `ccminer`.
- Make sure the device has execution permission for the binary.

## License
This project is distributed under the MIT License.

