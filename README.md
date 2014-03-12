## Intro ##

* **AUTHOR**: Rob dot Tillaart at gmail dot com  modified at 0.3 by Gil Ross at physics dot org
* **VERSION**:PURPOSE: Recursive statistical library for Arduino

## NOTE##
2011-01-07

Gill Ross Rob Tillaart's Statistic library uses one-pass of the data (allowing each value to be discarded), but expands the Sum of Squares Differences to difference the Sum of Squares and the Average Squared. This is susceptible to bit length precision errors with the float type (only 5 or 6 digits absolute precision) so for long runs and high ratios of the average value to standard deviation the estimate of the standard error (deviation) becomes the difference of two large numbers and will tend to zero.

For small numbers of iterations and small Average/SE th original code is likely to work fine. It should also be recognised that for very large samples, questions of stability of the sample assume greater importance than the correctnness of the asymptotic estimators.

This recursive algorithm, which takes slightly more computation per iteration is numerically stable.
It updates the number, mean, max, min and SumOfSquaresDiff each step to deliver max min average, population standard error (standard deviation) and unbiassed SE.

##  HISTORY ##
* 0.1 - 2010-10-29 initial version
* 0.2 - 2010-10-29 stripped to minimal functionality
* 0.2.01 - 2010-10-30 added minimim, maximum, unbiased stdev, changed counter to long -> int overflows @32K samples
* 0.3 - branched from 0.2.01 version of Rob Tillaart's code Released to the public domain