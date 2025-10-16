# RATS

This Repositiry includes estimators and test statistics for non-stationary processes, which I wrote with software RATS (Regression Analysis for Time Series)[^1] between 1998 and 2004.[^2] You'll find the following routines:

- [__fmols.scr__](fmols.src): performs fully modified estimation of cointegrating regressions between a pair of variable, using an automatic bandwidth. It also tests for the constancy of the cointegrating regressions using the Hansen's (1992) $L_c$ test of parameter instability; see Hansen, B. E., 1992, Tests for parameter instability in regressions with I(1) processes, Journal of Business & Economic Statistics, 10(3), pp. 321-335. The code slightly followed Peter Pedroni's group-fm.prg/pangroup.prg_, which no longer exists at Estima to my knowledge. Peter's original code was later extended to [panelfmprocedure](https://estima.com/webhelp/topics/panelfmprocedure.html) by the Estima team. Estimation and test apply to a pure time series model. Estima revised the routine notably to handle command options; see the header within the [fmols.src file at estima.com](https://www.estima.com/procs_perl/fmols.src). I am writting down the different estimation steps in file [fmols_theory](fmols_theory.md), forthcoming ...

- [adfjtest.src](adfjtest.src) ... forthcoming

[^1]: I'd like to thank Tom Doan for having developed RATS.

[^2]: I started to write the routine while I was research associate in the Centre for Competition Policy at University of East Anglia, Norwich.
