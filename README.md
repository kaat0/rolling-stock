# Rolling Stock Data

[![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-green.svg)](https://creativecommons.org/licenses/by/4.0/)

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

The vehicle YAML-files follow the [railtoolkit rolling stock schema (2022.04)](https://github.com/railtoolkit/schema).

# Usage

TODO

# Contributing

1. See if the vehicle is already available under a different name.
2. Check \<VEHICLE-NAME\>.yaml against [railtoolkit rolling stock schema](https://github.com/railtoolkit/schema).
3. Create a Pull Request with:
    - \<CATEGORY\>/\<VEHICLE-NAME\>.yaml
    - your Name added in CITATION.cff

# Data Collection Guide

## Resistance

![x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}](https://latex.codecogs.com/svg.latex?x=\frac{-b\pm\sqrt{b^2-4ac}}{2a})
(in ‰)
traction units:
    F_Rt = f_Rtd0 * m_td * g + f_Rtc0 * m_tc * g + F_Rt2 * ((v+Δv_t)/v00)^2
the consist (set of wagons):
    F_Rw = m_w * g * (f_Rw0 + f_Rw1 * v/v00 + f_Rw2 * ((v+Δv_w)/v00)^2)

## Tractive Effort

# Roadmap

* provide a YAML file generator for rolling stock data.

------------

# License

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
