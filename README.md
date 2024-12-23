# RATS

This Repositiry includes estimators and test statistics for non-stationary processes, written with software RATS (Regression Analysis for Time Series).[^1] I used RATS between 1998 and 2004. You'll find the following routines:

- [__fmols.scr__](fmols.src): performs fully modified estimation of cointegrating regressions between a pair of variable, using an automatic bandwidth. It also tests for the constancy of the cointegrating regressions using the Hansen's (1992) L_c test of parameter instability; see Hansen, B. E., 1992, Tests for parameter instability in regressions with I(1) processes, Journal of Business & Economic Statistics, 10(3), pp. 321-335. The code slightly followed Peter Pedroni's group-fm.prg/pangroup.prg_, which no longer exist to my knowledge. I aplied significant modifications made to his program. Peter's original code was later extended to [panelfmprocedure](https://estima.com/webhelp/topics/panelfmprocedure.html) by the Estima team. The estimation and test are performed for a pure time series model. I wrote this routine in 2002 while I was research associate in the Centre for Competition Policy at University of East Anglia, Norwich. Estima applied corrections to the routine notably to handle command options; see the header within the [fmols.src file at estima.com](https://www.estima.com/procs_perl/fmols.src).
- forthcoming

[^1]: I'd like to thank Tom Doan for having developed RATS.
