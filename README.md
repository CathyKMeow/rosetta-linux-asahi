# Hacked RosettaLinux that runs on Asahi Linux
## A 4k-page kernel is required

### Download:
[![Patch](https://github.com/CathyKMeow/rosetta-linux-asahi/actions/workflows/patch.yml/badge.svg)](https://github.com/CathyKMeow/rosetta-linux-asahi/actions/workflows/patch.yml)

### To extact and patch yourself:
``` bash
# macOS
pkgutil --check-signature RosettaUpdateAuto.pkg
pkgutil --expand-full RosettaUpdateAuto.pkg RosettaUpdateAuto.pkg-expanded
cp RosettaUpdateAuto.pkg-expanded/RosettaUpdateAuto.pkg/Payload/Library/Apple/usr/libexec/oah/RosettaLinux/rosetta ./rosetta
dd if=<(printf '\x1f\x20\x03\xd5') of='rosetta' bs=1 seek=170828 conv=notrunc
dd if=<(printf '\x1f\x20\x03\xd5') of='rosetta' bs=1 seek=170856 conv=notrunc
```

### Rosetta also runs on other ARM64 machines after being patched, but that's not legal. Please use FEX / Box64 instead.
