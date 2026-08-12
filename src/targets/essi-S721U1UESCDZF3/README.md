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
aarch64`, matching the shared `android14-6.1` Samsung KernelSU late-load pair.

The profile and build artifacts are statically verified but hardware-untested.
