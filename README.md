# Stereo TDA7293

This is a PCB design for a stereo amplifier, using a TDA7293 for each channel.

## Power

The board requires 36+36V DC.  Filtering caps are included, but a bridge 
rectifier is not as this is expected to be used with a switching supply.

## Unmute

The muting circuits are controlled via an opto-isolated input.  Provide 
5-24VDC on the UNMUTE port to enable the amplifiers.  This port allows the
amplifier to be put into a standby/mute mode, e.g. while preamplifiers are
booting.

## Components

Input capacitors shall be film-type box capacitors, 5mm lead pitch.

C2 and C8 should be non-polarised 22uF electrolytics, as high-voltage as will
fit in the footprint (8mm with 3.5mm lead pitch).

The bootstrap capacitors can (for each amplifier) be either a set of three 10uF 
MLCC, or a single electrolytic.  They must be rated for at least 50V.

All resistors in the signal chain (R1, R2, R3, R5, R6, R8) should be thin-film
metal precision resistors.

The output zobels (R4/C6, R9/C12) are probably only necessary with a TDA7294,
and may be omitted if there is absolutely no chance of shorting the amplifier
leads, e.g. through use of insulated plugs instead of bare wires into screw
terminals.  R4 and R9 should be 2W-rated.

Indicator LEDs may be omitted - there is one for each supply rail, and one that
lights with the UNMUTE signal is asserted.  No clip indication LEDs are offered.

## TDA7294

To use the board with a TDA7294, it is necessary to short between pins 12 and 14
of each amplifier, as indicated by a line on the rear silk-screen.  Failure
to provide this short will mean the bootstrap capacitor does not operate, and
the signal will have positive peaks clipped at higher power levels.

## License

This hardware design is (C) 2021 William Brodie-Tyrrell and is licensed under 
the CERN OHL; see cern_ohl_v_1_2.pdf
