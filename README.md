Physical Modeling Saxophone Development
=======================================

by Manuel Planton 2019

for Musical Acoustics Seminar at the Institute for Electronic Music and Acoustics, Graz.

Starting from a basic physical model of a clarinet out of the Pure Data waveguide library "acre/wg" by Winfried Ritsch, a physical modeling saxophone synthesizer has been developed.
The [seminar paper](Seminararbeit_Manuel_Planton.pdf) is in german and shows the research and development.


Installation:
-------------

1. Install *iemlib*.

2. Create a directory lib/ and clone [acre](https://git.iem.at/pd/acre) and [acre-wg](https://git.iem.at/pd/acre-wg).

3. Rename lib/acre-wg to wg.


Files and directories:
----------------------

| file or directory    | explanation     |
| -------------------- | --------------- |
| abs/                 | pd-abstractions |
|lib/                  | libraries       |
|pm_sax_development.pd | main pd patch for physical modeling saxophone development |
|preset.txt            | presets for the main patch|
|README.md             | this file       |


Development and Comparison:
---------------------------

* clarinet A: original clarinet from the wg-lib


* clarinet B: fixed slope m in the rho_hat function of the reed


* clarinet C:

  - controllable parameter h_delta_c (Reed stiffness and embachoure. In the patch h_delta_c is referred to as h_c for convenience)
  
  - complementary reflection and transmission filters of the bell with the same cutoff frequency

  - controllable parameter portamento (waveguide delay fade time)


* clarinet D: added parameter k as exponent of rho_hat for brightness control of the reed or mouthpiece


Implementations of Instruments proposed by Scavone (2002) in [Time-Domain Synthesis of Conical Bore Instrument Sounds](http://hdl.handle.net/2027/spo.bbp2372.2002.003)


* sax A: a reed attached to a conical bore

  - This instrument is mostly unstable because of a delay-free loop, which is mentioned in the paper


* sax B: The "Cyclone"

  - Stabalized model because of the use of a mouthpiece/cylinder junction
  
  - A reed attached to a cylindrical bore, which turns into a cone

  - difficult parameter set


* sax C: The virtual "Blowed String"

  - It "incorporates an open-open cylindrical air column structure" and the non-linear reed function also used in the other instruments, "applied at a 'blowing' point which can be varied along the length of the pipe".
  
  - can sound similar to a saxophone
  
  - not a physical model corresponding to the real world


Up to here all physical models change their fundamental frequency according to the played note by adjusting the bore length. Toneholes, radiation effects or dissipation are not modeled in these instruments.

