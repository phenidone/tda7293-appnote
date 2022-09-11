# Stereo TDA7293

This is a PCB design for a stereo amplifier, using a TDA7293 for each channel.

## Power

The board requires 36+36V DC for 8R loads.  Filtering caps are included, but 
a bridge rectifier is not as this is expected to be used with a switching supply.

## Unmute

The muting circuits are controlled via an opto-isolated input.  Provide 
5-24VDC on the UNMUTE port to enable the amplifiers.  This port allows the
amplifier to be put into a standby/mute mode, e.g. while preamplifiers are
booting and power supplies are stabilising.

## Components

Input capacitors shall be film-type box capacitors, 5mm lead pitch.

C3 and C9 should be non-polarised 22uF electrolytics, as high-voltage as will
fit in the footprint (8mm with 3.5mm lead pitch).

All resistors in the signal chain (R1, R2, R3, R13, R14, R15) should be thin-film
metal precision resistors.

Loop-break resistors (R7, R8, R17, R18) can be chosen differently in accordance
with different grounding needs, e.g. where multiple modules are powered from a
single PSU but receiving signal from a third preamplifier board.  Their
selection depends on your ground topology.

The output zobels (R5/C6, R16/C12) are probably only necessary with a TDA7294,
and may be omitted if there is absolutely no chance of shorting the amplifier
leads, e.g. through use of insulated plugs instead of bare wires into screw
terminals.  R5 and R16 should be 2W-rated.

## TDA7294

The board charges the bootstrap capacitor from the OUTPUT pin rather than
the BOOTLOAD pin, so this board will also work unmodified with a TDA7294.
That limits the absolute-max supply voltage to 100V rather than 120V, but
the appropriate level is lower than that anyway unless you have a very high
impedance load.

## License

This hardware design is (C) 2021 William Brodie-Tyrrell and is licensed under 
the CERN OHL; see cern_ohl_v_1_2.pdf

## TRL

Rev.A is tested and working, but has not been subjected to EMI or other
regulatory testing.

Rev.B has been manufactured but not tested.
