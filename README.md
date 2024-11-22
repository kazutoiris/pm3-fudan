# Proxmark3 for Fudan Card Full Data Extraction

One-click extraction of fully encrypted Fudan card data.

## License

This project is licensed under the GPLv3, same as the license of `RfidResearchGroup/proxmark3` .

## Contribute

All code is sourced from the `RfidResearchGroup/proxmark3` repository. Special thanks to Philippe Teuwen and other contributors for their work in developing and open-sourcing this code.

## Usage

1. Download or compile the Proxmark3 client. (Precompiled builds can be downloaded from [https://www.proxmarkbuilds.org/](https://www.proxmarkbuilds.org/)). **Ensure that the client and firmware versions match!**

2. Download the necessary binary from the release.

3. Download `fm11rf08s_recovery.py` from this repository.

    Make sure to place all the files in the same directory. The file structure should look like this:

	```
	./
	│   fm11rf08s_recovery.py
	│   nonce2key.exe
	│   staticnested_0nt.exe
	│   staticnested_1nt.exe
	│   staticnested_2nt.exe
	│   staticnested_2x1nt_rf08s.exe
	│   staticnested_2x1nt_rf08s_1key.exe
	└───client
	    │   pm3
	    │   pm3-flash
	    │   pm3-flash-all
	    │   pm3-flash-bootrom
	    │   pm3-flash-fullimage
	    │   proxmark3.exe
	    │   setup.bat
	    │   // ...spin...
	    └───libs
	    └───// ...spin...
	```

4. Run `fm11rf08s_recovery.py --port COM1`, `COM1` is the serial port of Proxmark3.

	The script will output something like this:

	```
	[+]  UID: 12 34 56 78
	[=] UID: 12345678
	[=] Getting nonces...
	[=] Generating first dump file
	[=] Data has been dumped to `hf-mf-12345678-dump.bin`
	[=] ----Step 1:  0 minutes  5 seconds -----------
	[=] Running staticnested_1nt & 2x1nt when doable...
	[=] Looking for common keys across sectors...
	[=] Saving duplicates dicts...
	[=] Computing needed time for attack...
	[=] ----Step 2:  0 minutes 27 seconds -----------
	[=] Still about  4 minutes 51 seconds to run...
	[=] Brute-forcing keys... Press any key to interrupt
	[=] Sector  0 keyA = 01234567890a
	[=] Sector  0 keyB = 01234567890a
	[=] Sector  1 keyB = 01234567890a
	[=] Sector  1 keyA = 01234567890a
	[=] Sector  2 keyB = 01234567890a
	[=] Sector  2 keyA = 01234567890a
	[=] Sector  3 keyB = 01234567890a
	[=] Sector  3 keyA = 01234567890a
	[=] Sector  4 keyB = 01234567890a
	[=] Sector  4 keyA = 01234567890a
	[=] Sector  5 keyB = 01234567890a
	[=] Sector  5 keyA = 01234567890a
	[=] Sector  6 keyA = 01234567890a
	[=] Sector  6 keyB = 01234567890a
	[=] Sector  7 keyA = 01234567890a
	[=] Sector  7 keyB = 01234567890a
	[=] Sector  8 keyA = 01234567890a
	[=] Sector  8 keyB = 01234567890a
	[=] Sector  9 keyA = 01234567890a
	[=] Sector  9 keyB = 01234567890a
	[=] Sector 10 keyA = 01234567890a
	[=] Sector 10 keyB = 01234567890a
	[=] Sector 11 keyA = 01234567890a
	[=] Sector 11 keyB = 01234567890a
	[=] Sector 12 keyA = 01234567890a
	[=] Sector 12 keyB = 01234567890a
	[=] Sector 13 keyA = 01234567890a
	[=] Sector 13 keyB = 01234567890a
	[=] Sector 14 keyA = 01234567890a
	[=] Sector 14 keyB = 01234567890a
	[=] Sector 15 keyA = 01234567890a
	[=] Sector 15 keyB = 01234567890a
	[=] Sector 32 keyB = 01234567890a
	[=] Sector 32 keyA = 01234567890a
	[=]
	[+] found keys:
	[+]
	[+] -----+-----+--------------+---+--------------+----
	[+]  Sec | Blk | key A        |res| key B        |res
	[+] -----+-----+--------------+---+--------------+----
	[+]  000 | 003 | 01234567890a | 1 | 01234567890a | 1
	[+]  001 | 007 | 01234567890a | 1 | 01234567890a | 1
	[+]  002 | 011 | 01234567890a | 1 | 01234567890a | 1
	[+]  003 | 015 | 01234567890a | 1 | 01234567890a | 1
	[+]  004 | 019 | 01234567890a | 1 | 01234567890a | 1
	[+]  005 | 023 | 01234567890a | 1 | 01234567890a | 1
	[+]  006 | 027 | 01234567890a | 1 | 01234567890a | 1
	[+]  007 | 031 | 01234567890a | 1 | 01234567890a | 1
	[+]  008 | 035 | 01234567890a | 1 | 01234567890a | 1
	[+]  009 | 039 | 01234567890a | 1 | 01234567890a | 1
	[+]  010 | 043 | 01234567890a | 1 | 01234567890a | 1
	[+]  011 | 047 | 01234567890a | 1 | 01234567890a | 1
	[+]  012 | 051 | 01234567890a | 1 | 01234567890a | 1
	[+]  013 | 055 | 01234567890a | 1 | 01234567890a | 1
	[+]  014 | 059 | 01234567890a | 1 | 01234567890a | 1
	[+]  015 | 063 | 01234567890a | 1 | 01234567890a | 1
	[+] -----+-----+--------------+---+--------------+----
	[+] ( 0:Failed / 1:Success )
	[=]
	[+] Generating binary key file
	[+] Found keys have been dumped to `hf-mf-12345678-key.bin`
	[+] Generating final dump file
	[+] Data has been dumped to `hf-mf-12345678-dump.bin`
	[+] Removing generated dictionaries...
	[=] ----Step 3:  4 minutes 30 seconds -----------
	[=] ---- TOTAL:  5 minutes  3 seconds -----------
	```

## Reference

Teuwen, P. (2024). *MIFARE Classic: Exposing the Static Encrypted Nonce Variant*. Cryptology ePrint Archive, Paper 2024/1275. Retrieved from [https://eprint.iacr.org/2024/1275](https://eprint.iacr.org/2024/1275)
