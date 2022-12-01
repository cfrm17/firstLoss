# Giant First Loss Methodology


Compared to the standard first loss model with the same collateral pool and tranche structure, the new model predicts smaller B/E spreads for each tranche. Further, it is more sensible to the interest rate and the sensitivity to the interest rate term structure changes dramatically. The B/E spreads for each tranche calculated by both models converge when the hazard rates of the obligors become very small.


The new Giant First Loss model is a first loss trade structure in which all losses to the structure are held until the maturity of the trade. In this model, the amount of the principal for the tranches, upon which the coupons are paid, are fixed for the duration of the structure, rather than being modified as losses occur for the standard first loss model. The value of protection is calculated by solely using the discount factor at maturity of the trade, because all losses are settled at maturity.

Within the existing modeling framework, the trade is implemented by resetting generated default times in each Monte Carlo (MC) scenario to be the maturity date. Compared with the standard first loss trade model, two trends of change can be perceived. First, when the hazard rate of the obligor becomes smaller, the B/E spreads for both models would converge to zero. Second, because in the new model the cash flow pattern for default events has changed, the sensitivity to the interest rate should be different. Generally the new model is not only more sensitive to the interest rate but the sensitivity to its term structure changes dramatically as well. 

First, the sensitivity to the interest rate for the new model and the standard first loss model is compared. The results are shown in Table 2 with the detail results listed in Appendix II. Delta with 5bps parallel shift is calculated by giving a 5bps parallel up shift to the interest rate. Delta with 5bps tilt is computed by giving a 5bps tilt to the interest rate (clockwise tilt within 5 years).

We can find two trends. First, the new model is more sensitive. Given the same amount of perturbation to the interest rate, the change of present value (PV) for the new model is much larger than that of the standard model. Second, the sensitivity to term structure changes dramatically. For the standard first loss model, the Delta change between the parallel shift and the tilt is small while the change is very large for the new model. 

These two trends meet our expectation of the change of the model, because in the new model all losses are accrued to the maturity and discounted with only one discount factor, which is the one at maturity. The discount factor at maturity has maximum sensitivity to the interest rate shift and tilt.

In the standard first loss model, the mean default time becomes larger if the hazard rate decreases. So the B/E spreads for two models should converge to zero if the hazard rate becomes smaller. To test this effect, we change the hazard rate of each obligor for the test trade 1 from 0.01bps to 500bps with correlation being 0.3 for the test deal. 

The B/E spreads for tranche 1 and tranche 2 are plotted in Figs.1 and 2, respectively, and the detail results are listed in Appendix III. It meets the expectation that two spreads converge to zero when the hazard rate becomes smaller. For the mezz tranche (tranche2) the spread actually become zero if the hazard rate is less than 0.01 bps.

It is found from Figs. 1 and 2 that the B/E spread of each tranche for the new model is always smaller than that of the standard first loss deal. This is due to a smaller discount factor for value of protection and a larger and fixed PV01 for each tranche in the new model.





To compare the new model with the available closed form solution, we construct a simple 5-year test trade in which 4 obligors are included. The detail of the test trade is shown in Appendix I.

In this test model the principal of the first tranche equals loss given default (LGD) of the obligors in the collateral pool. This makes the first tranche equivalent to the first to default basket. With no counterparty risk, there is a closed form solution for the B/E spread of the first tranche:

 .

 is the discount factor,   is the fee payment dates of the trade,   is the daycount fraction, and   is the maturity of the trade. With the set of obligors  and its subset  ,   is a hazard rate known as
	
 .

The definition of   can be found. 

The Giant First Loss trade model is a first loss model in which all losses to the structure are held until the maturity of the trade. Based on the existing standard first loss model, the implementation of the trade is straightforward. The results confirm that the submitted model is implemented correctly.

In the new model, the total coupon paid on each tranche is known a priori.  The value of protection is calculated by setting all losses to be at maturity thus discounted solely by the discounted factor at maturity. Compared with standard first loss trade, this changes lead to smaller B/E spreads for each tranche, higher sensitivity to the interest rate, and a dramatic change of sensitivity to the interest rate term structure. 

The PV01 is fixed for the new model if there is no settlement risk and counterparty risk. Both settlement risk and counterparty risk tend to decrease the value of PV01 thus increase the B/E spread of each tranche.

Without considering settlement risk and counterparty risk, the results generated by MC simulation meet the closed form results very well (see https://finpricing.com/lib/FiZeroBond.html), indicating that the numerical implementation of the new GiantFirstLoss trade is correct.
 

