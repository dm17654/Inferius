# Inferius
Inferius is an [xpwn](https://github.com/m1stadev/xpwn)-like tool to create & restore custom IPSWs to 64-bit devices.

Its current purpose is to downgrade devices (vulnerable to [checkm8](https://github.com/axi0mX/ipwndfu)) to previous iOS versions. However, there are other possible uses for this tool as well.

## Notes and Caveats
Before using Inferius, keep in mind that
- **No one but YOU** is fully responsible for any data loss or damage caused to your device
- Restores are **not** untethered. This means that in order to boot your device, you're required to use [PyBoot](https://github.com/MatthewPierson/PyBoot), [ra1nsn0w](https://github.com/tihmstar/ra1nsn0w), or [Ramiel](https://ramiel.app/) to do just that (or if you want to boot jailbroken, [checkra1n](https://checkra.i/n) should work as well).
- Downgrades are still limited to versions compatible with the latest signed SEP version. This will change when [checkra1n](https://checkra.in/) implements a nonce setter for the SEP.

Inferius may not come with a firmware bundle compatible with your device. If you need to create your own firmware bundle, you can follow [this guide](https://github.com/m1stadev/Inferius/wiki/Creating-your-own-Firmware-Bundles).

[Pull requests](https://github.com/m1stadev/inferius-ext/compare) for new firmware bundles are welcome, as long as the firmware bundle you want to add can create a usable IPSW for the targeted version.

## Usage
```py
./inferius -d 'identifier' -f 'IPSW' [-c/-r] [-v]
```

| Option (short) | Option (long) | Description |
|----------------|---------------|-------------|
| `-d IDENTIFIER` | `--device IDENTIFIER` | Device identifier |
| `-f IPSW` | `--ipsw IPSW` | Path to IPSW |
| `-c` | `--create` | Create custom IPSW |
| `-r` | `--restore` | Restore custom IPSW |
| `-b` | `--bundle BUNDLE` | (Optional) Specify path to local Firmware Bundle |
| `-u` | `--update` | Keep data while restoring custom IPSW |

## Requirements
- A computer running macOS or Linux
- At least **10gbs** of free space on your computer
- An Internet Connection
- A 64-bit device (vulnerable to [checkm8](https://github.com/axi0mX/ipwndfu))
- A firmware bundle for your device & the iOS version to be downgraded to
- A brain (Not completely necessary, but YMMV)
- [libusb](https://libusb.info/)
- [My fork of futurerestore](https://github.com/m1stadev/futurerestore)
    - futurerestore must be compiled with [my fork of img4tool](https://github.com/m1stadev/img4tool), or else it can't be used with Inferius.
- [libirecovery](https://github.com/libimobiledevice/libirecovery)
- [tsschecker](https://github.com/1Conan/tsschecker)
- Pip dependencies:
    - `pip3 install -r requirements.txt`

## To-Do
- Re-implement iOS 10 downgrades for A7 devices.
- Update bundle documentation

## Special thanks
I'd like to thank the following people for their corresponding role in this project
- [NotHereForTheDong](https://github.com/NotHereForTheDong) for providing firmware bundles and beta testing
- [tale](https://twitter.com/aarnavtale), [Chibibowa](https://twitter.com/Chibibowa), and [Moses](https://twitter.com/MosesBuckwalter) for beta testing

Finally, if you need help or have any questions about Inferius, join my [Discord server](https://m1sta.xyz/discord).
