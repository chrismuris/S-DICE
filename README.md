# DICE-Simplified

The code in this repository is provided under the MIT license, see LICENSE. Every attempt has been made to do justice to existing rights. Please let us know if these have nevertheless been violated and we shall be happy to acknowledge these rights.

It accompanies ["DICE Simplified" (2021), by Ikefuji, Laeven, Magnus, and Muris, in Environmental Management and Assessment (26)](https://link.springer.com/article/10.1007/s10666-020-09738-2).

This code is a modification of GAMS code available (as of November, 2022) via the [homepage of William D. Nordhaus](https://williamnordhaus.com/dicerice-models). That website provides GAMS code for DICE (Dynamic Integrated model of Climate and the Economy). To learn more about GAMS, start from the Wikipedia entry on [GAMS](https://en.wikipedia.org/wiki/General_algebraic_modeling_system).

Ikefuji et al. (2021) describe DICE in Section 2, and introduce the S-DICE models (simplified DICE) in Section 6. Each of the four files in this repository implement an S-DICE model. The name of the file corresponds to the model names on p. 8-9 of Ikefuji et al., see also Figure 6.

For example, the file `SICE_00MH.gms` implements the model referred to as *00MH*, etc.
The four files have acronyms:

- *00MH*
- *0DMH*
- *m0MH*
- *mDMH*

All files end in *MH*, indicating that we have changed the CO2 concentration equation (*M*) and temperature equation (*H*) relative to DICE. 
If the first entry is *m*, the code provides an upper bound of 1.0 on the fraction $\mu$, by setting `limmiu / 1.0`. If the entry is 0, we use DICE's value of 1.2 for the upper bound.
If the second entry is *D*, we use a damage function that is different from DICE, see Ikefuji et al. (2021), by changing the `yy(t)..` equation.

Running any of the four .gms files produces a .csv file with the same file name in the base directory containing model outputs. See lines 340 and after in the .gms file to see a list of the variables written to this output file. 

## News

- November 24, 2022: Posted version 1.
- December 6, 2022: Posted version 2.