# Rolling Stock Data

[![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-green.svg)](https://creativecommons.org/licenses/by/4.0/) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.6467448.svg)](https://doi.org/10.5281/zenodo.6467448) [![continuous integration test](https://github.com/railtoolkit/rolling-stock-data/actions/workflows/testing.yaml/badge.svg?branch=main)](https://github.com/railtoolkit/rolling-stock-data/actions/workflows/testing.yaml)

------------

# About

This repo is a collection of rail vehicle data. This is a place to collect this data since there is little vehicle data publicly available and the research is complex. Everyone is allowed to use the data and also to contribute new data.

| Category           | Content                                                         |
| ------------------ | --------------------------------------------------------------- |
| freight wagon      | vehicles for cargo transport without traction power             |
| multiple unit      | composed vehicles with traction power which cannot be decoupled |
| passenger carriage | vehicles for passenger transport without traction power         |
| traction unit      | single vehicles with traction power                             |

Categories are derived from [TSI LOC&PAS](https://eur-lex.europa.eu/legal-content/en/TXT/PDF/?uri=OJ:JOL_2014_356_R_0004&from=EN) and [TSI WAG](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32013R0321&qid=1649681414325&from=EN).

The vehicle YAML-files follow the [railtoolkit rolling stock schema (2022.05)](https://github.com/railtoolkit/schema).

------------

# Data Collection Guide

## Resistance

The vehicle resistance force ![F_R](https://latex.codecogs.com/svg.latex?F_R) is calculated in Newton. But for better compatibility with other resistances, the force is set in relation to the mass ![m](https://latex.codecogs.com/svg.latex?m) of the vehicle and the force of gravity ![g](https://latex.codecogs.com/svg.latex?g):

![f_R = \frac{F_R}{m \cdot g}](https://latex.codecogs.com/svg.latex?f_R%20=%20\frac{F_R}{m%20\cdot%20g})   (in ‰)

The calculation of the resistance follows the general formula:
![f_R=\alpha+\beta\cdot v+\gamma\cdot v^2](https://latex.codecogs.com/svg.latex?f_R%20=%20\alpha%20+%20\beta%20\cdot%20v%20+%20\gamma%20\cdot%20v^2)  (in ‰)

|    variable                                            | vehicle attribute    |
| ------------------------------------------------------ | -------------------- |
| ![\alpha](https://latex.codecogs.com/svg.latex?\alpha) | `base_resistance`    |
| ![\beta](https://latex.codecogs.com/svg.latex?\beta)   | `rolling_resistance` |
| ![\gamma](https://latex.codecogs.com/svg.latex?\gamma) | `air_resistance`     |

For vehicles with propulsion, the attribute `rolling_resistance` is used only for the non-driven axles.

Sources with tables for ![\alpha](https://latex.codecogs.com/svg.latex?\alpha), ![\beta](https://latex.codecogs.com/svg.latex?\beta), and ![\gamma](https://latex.codecogs.com/svg.latex?\gamma) are for example:
  * Wende, Dietrich. [Fahrdynamik des Schienenverkehrs](https://doi.org/10.1007/978-3-322-82961-0). Germany: Vieweg+Teubner Verlag, 2013.
  * Brünger, Olaf and Dahlhaus, Elias. Running Time Estimation, Chaper 4, Pages 65 - 90. In: Railway Timetabling & Operations. Germany: Eurailpress, 2008.


## Tractive Effort

The tractive force of a traction unit is characterised by two limit forces:
* the maximum force that can be transmitted between wheel and rail ![F_{TF}(v) = m \cdot g \cdot \mu(v)](https://latex.codecogs.com/svg.latex?F_{TF}(v)%20=%20m%20\cdot%20g%20\cdot%20\mu(v)), and 
* the maximum tractive force of the traction unit due to power ![F_{TP}(v) = \frac{P}{v}](https://latex.codecogs.com/svg.latex?F_{TP}(v)%20=%20\frac{P}{v}).

Both limit forces shape the characteristics of the traction unit. The pairs for `tractive_effort` can be approximated from both conditions. At the very least, three `tractive_effort` pairs are needed:
  * The maximum transmittable force at standstill is limited by the coefficient of friction and the mass on the drive axles.
  * The speed at the transition from the frictional traction force to the power traction force.
  * The maximum force during the maximum speed.

As public sources rarely know the actual forces achieved the above values are only an approximation. What can be found publicly, however, is the mass on the driven axles and the installed power.

------------

# Roadmap

  * provide a YAML file generator for rolling stock data.

------------

# License

Creative Commons Attribution 4.0 International Public License

This is a human-readable summary of (and not a substitute for) the license.

## You are free to:

Share — copy and redistribute the material in any medium or format
Adapt — remix, transform, and build upon the material for any purpose, even commercially.
This license is acceptable for Free Cultural Works.
The licensor cannot revoke these freedoms as long as you follow the license terms.

## Under the following terms:

Attribution — You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
No additional restrictions — You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.

## Notices:

You do not have to comply with the license for elements of the material in the public domain or where your use is permitted by an applicable exception or limitation.
No warranties are given. The license may not give you all of the permissions necessary for your intended use. For example, other rights such as publicity, privacy, or moral rights may limit how you use the material.
