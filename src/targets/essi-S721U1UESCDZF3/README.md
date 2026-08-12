# essi-S721U1UESCDZF3

```text
device: Samsung Galaxy S24 FE (SM-S721U1, essi)
firmware: S721U1UESCDZF3 / US unlocked
display build: BP4A.251205.006.S721U1UESCDZF3
fingerprint: samsung/r12suew/r12s:16/BP4A.251205.006/S721U1UESCDZF3:user/release-keys
kernel: 6.1.157-android14-11
```

`target.h` contains the exact symbol, layout, physical-load, trace, and KASLR
values recovered from that firmware. `p0_fingerprint.h` contains 32 target
kernel page fingerprints and was checked against all 256 source qwords.

The kernel vermagic is `6.1.157-android14-11 SMP preempt mod_unload modversions
aarch64`. The manifest pairs this profile with the device-tested S24 (e1s)
no-patch-text KernelSU late-load binary: the generic Samsung 6.1 module panics
in Samsung/Exynos EL2 while attempting live text patching, and the e1s module
avoids that path. Its 202 undefined imports all resolve against the recovered
S721U1 vmlinux (zero missing, zero CRC mismatches).

This is a 4K-page Exynos 6.1 build, so the exploit uses the device-tested
4K tuning shared with the S24/S24+ profiles (`SKB_DATA_DELTA -0x1000`,
`PSELECT_WORD_SHIFT 3`, `BANK_SLOTS 5`, `BANK_TASK_OFF 0x3200`), not the
generator's 16K-page defaults.

The profile and build artifacts are statically verified but hardware-untested.
