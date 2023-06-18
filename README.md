# nextz80
NextZ80 FPGA processor features:
1. All documented / un-documented instructions are implemented.
2. All documented / un-documented flags are implemented.
4. All (doc / un-doc) flags are changed accordingly by all (doc /un-doc) instructions. The block instructions (LDx,  CPx,  INx,  OUTx) have only the documented effects on flags. The Bit n, (IX/IY+d) and BIT n, (HL) undocumented flags XF and YF are implemented like the BIT n, r and not actually like on the real Z80 CPU.
5. All interrupt modes implemented: NMI, IM0, IM1, IM2
6. R register available.
7. Fast conditional jump/call/ret takes only 1 T state if not executed.
8. Fast block instructions: LDxR - 3 T states/byte, INxR/OTxR - 2 T states/byte, CPxR - 4 T states / byte.
9. Each CPU machine cycle takes (mainly) one clock T state. This makes this processor over 4 times faster than a Z80 at the same clock frequency (some instructions are up to 10 times faster). 
10. Works at up to 40MHZ on Spartan XC3S700AN speed grade -4).
11. Small size (~12%, ~700 slices - on Spartan XC3S700AN).
13. tested with ZEXDOC (fully compliant) and with ZEXALL (all OK except CPx(R),  LDx(R),  BIT n, (IX/IY+d),  BIT n, (HL) - fail because of the un-documented XF and YF flags).
