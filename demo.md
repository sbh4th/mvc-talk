Why Am I Here?

0.5

-   Smarter Choices involves $\rightarrow$ producing evidence about
    interventions.

0.5

![image](SG-AL4.png){width=".9\\textwidth"}

0.4

-   In this talk I want to discuss how to make \"smarter choices\" when
    producing that evidence.

0.6

![image](SG-NL-perinatal.png){width="100%"}

Background
==========

[^1]

![image](0_Users_samharper_Dropbox_work_research_projects_FARS_mvc-bayes_work_talk_oecd-mvc-trends.png){width="0.9\\paperwidth"}

Context of Motor Vehicle Deaths in USA

-   Seat belt use reduces motor vehicle crash (MVC) deaths.

-   First mandatory seat belt law in 1984 (NY state).

-   Evidence that mandatory seat belt laws:

    -   Increase seat belt use.

    -   Reduced MVC death rates.

-   Current laws come in two varieties:

    -   Secondary enforcement: Consequent to another violation

    -   Primary enforcement: Seen not wearing seat belt

-   Presently, 35 states with primary enforcement, 15 with secondary.

Question

Should states with secondary enforcement upgrade to primary?

Current laws as of 2017 [^2]

![image](1_Users_samharper_Dropbox_work_research_projects_FARS_mvc-bayes_work_talk_figA2a.png){width="0.85\\paperwidth"}

[^3]

![image](2_Users_samharper_Dropbox_work_research_projects_FARS_mvc-bayes_work_talk_bergal-collated.png){width="0.85\\paperwidth"}

Should Colorado upgrade to primary?

![image](3_Users_samharper_Dropbox_work_research_projects_FARS_mvc-bayes_work_talk_co-cdot-quote.png){width="0.9\\paperwidth"}

Hang on\... [^4]

0.6

-   \"CDOT should be concerned with building and maintaining our roads.
    Not joining the nanny crowd trying to protect us from our own bad
    decisions.

-   \...Darwinism exists for a reason. If people want to meet their
    windshields at 60 miles and hour and remove themselves from the gene
    pool, that might be good for us in the long run.

-   It's not a difficult sell to ask people to save their own lives.
    [But it shouldn't be done at gunpoint]{style="color: red"}.\"

0.4

![image](co-concerned.png){width=".9\\textwidth"}

Potential unintended consequences ("Driving While Black") [^5]

![image](4_Users_samharper_Dropbox_work_research_projects_FARS_mvc-bayes_work_talk_aclu-disparities.png){width="0.9\\paperwidth"}

Rationale for Bayesian evaluation

-   Prior evidence on primary laws:

    -   Strong evidence they reduce deaths and increase seat belt use;

    -   This evidence is dated (1990s, early 2000s).

-   16 states have upgraded to primary since 2000.

Our aims:

1.  Evaluate recent policy changes.\*[^6]

2.  Combine the evaluation of recent data with prior evidence.

3.  Provide updated evidence on the impact of upgrading to primary
    enforcement.

Intuition for Bayesian analysis

-   We will generate new empirical evidence on the impact of policy
    changes since 2000.

-   How should we approach inference from this study?

```{=html}
<!-- -->
```
-   Frequentist analysis assumes **zero** background information.

-   Equivalent to belief that primary laws just as likely to:

    -   Decrease death rates by a factor of 100 or 10*;*

    -   *Increase* death rates by a factor 10 or 100.

```{=html}
<!-- -->
```
-   Bayesian inference explicitly incorporates prior information to
    estimate the posterior probability distribution:

$$\underbrace{P(\theta|D)}_{\textrm{posterior probability}}\propto\underbrace{P(D|\theta)}_{\textrm{ likelihood }}\times\underbrace{P(\theta)}_{\textrm{prior probability}}$$

Prior empirical evidence on upgrades to primary enforcement

-   3 high-quality studies on MVC death rates:[^7]

-   Mean estimate: -0.5 deaths/billion VMT (-0.7,
    -0.3)[$\rightsquigarrow$1500 deaths/yr.]{style="color: red"}

-   Prediction interval for new trial: (-1.97,
    0.94).[$\rightsquigarrow$(-6000, +3000).]{style="color: red"}

-   On relative scale $RR=0.95$, $95\%CI=0.83,1.09$

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/meta-mvc.png){width="0.95\\paperwidth"}

Prior empirical evidence on upgrades to primary enforcement

-   6 moderate-quality studies on proportion belted:[^8]

-   Average estimate: 0.13 (0.10, 0.16). [$\rightsquigarrow$13
    percentage points.]{style="color: red"}

-   Prediction interval for new "trial": (0.03, 0.23).

-   On relative scale $RR=1.3$, $95\%CI=1.08,1.58$

![image](5_Users_samharper_Dropbox_work_research_projects_FARS_mvc-bayes_work_talk_meta-pb.png){width="0.95\\paperwidth"}

Methods
=======

Semi-Bayesian analysis via data augmentation

-   Data augmentation expresses prior information by adding empirical
    observations to the observed data.[^9]

How to execute:

1.  Define priors.

2.  Encode priors as observations and add to the observed data.

3.  Conduct analysis on all data.

4.  Regression estimate and 95% CI provide approximations to Bayesian
    posterior mean and credible interval.

-   Advantages:

    -   Avoids cumbersome full Bayesian machinery (resampling, MCMC).

    -   Approximates the posterior distribution.

How do we augment the observed data?

-   Suppose we were 95% sure the true $RR$ is between (0.25, 4).

-   What kind of data would correspond to the prior?[^10]

```{=html}
<!-- -->
```
-   Imagine we had a small randomized evaluation of upgrading to primary
    enforcement:

  -------- --------- ----------- -- -----------------------------
            Primary   Secondary     Estimates
   Deaths      4          4         $RR_{prior}=1.0$
    Pop     100,000    100,000      $95\%CI_{prior}=(0.25,4.0)$
                                    
  -------- --------- ----------- -- -----------------------------

-   Add these prior data to our observed data as an additional stratum.

Construction of priors

-   Semi-Bayes: we only include priors on a single parameter (the law).

-   Specify prior interval for the $RR$, translated into mean and
    variance.

```{=html}
<!-- -->
```
-   3 sets of priors:

1.  **Non-informative**: similar to frequentist assumptions.

2.  **Empirical**: prediction interval from prior meta-analysis.

    -   MVC: 95% bet true $RR$ between 0.83, 1.09
        [$\rightsquigarrow N(ln(0.95),0.005)$]{style="color: blue"}

    -   %belted: 95% bet true $RR$ between 1.08, 1.58
        [$\rightsquigarrow N(ln(1.30),0.009)$]{style="color: blue"}

3.  **Subjective**: from existing policy documents.\*

    -   Estimate 7-8% reduction on fatalities, 12 to 18 percentage
        points on seat belt use.[^11]

    -   We add some additional uncertainty around these estimates.

Summary of prior record construction

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/t1rr.png){width="0.95\\paperwidth"}

Data

-   Person-level data on fatal crashes and vehicle miles traveled (VMT)
    from the Fatal Analysis Reporting System (FARS), 2000-2016.

    -   Aggregate to 10 ages, 50 states, 17 years (n=8500, $\sim$400k
        deaths).

-   Dates of primary enforcement upgrades from the Insurance Institute
    for Highway Safety.

-   Other time-varying state policies:

    -   Speed limits;

    -   Graduated driver's license programs;

    -   Blood alcohol content laws.

-   Other time-varying state covariates:

    -   Police per capita;

    -   Per capita alcohol consumption;

    -   Median income.

Study design: Difference-in-Differences [^12]

-   Use pre/post data on treated and control groups to estimate the
    effect of policy.

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/ryan-fig1.png){width="0.9\\textheight"}

Likelihood model specifications

-   For MVC death rates, Poisson model, i.e.,
    $y_{ast}\sim Poisson(\mu_{ast})$:

$$ln(\mu_{ast})=\alpha+{\color{red}\beta\times Primary_{st}}+\boldsymbol{\gamma}\mathbf{A}_{ast}+\boldsymbol{\delta}\mathbf{Z}_{st}+\boldsymbol{\sigma}_{s}+\boldsymbol{\tau}_{t}+ln\left(VMT_{ast}\right)$$

-   For proportion belted, grouped logit model:

$$ln\left(p_{ast}/[1-p_{ast}]\right)=\alpha+{\color{red}\beta\times Primary_{st}}+\boldsymbol{\gamma}\mathbf{A}_{ast}+\boldsymbol{\delta}\mathbf{Z}_{st}+\boldsymbol{\sigma}_{s}+\boldsymbol{\tau}_{t}$$

-   where ($Primary=1$ when a primary enforcement law is in effect), and
    $\boldsymbol{\gamma}$, $\delta$, $\boldsymbol{\sigma}$, and
    $\mathsf{\boldsymbol{\tau}}$ represent vectors of coefficients for
    age groups, other time-varying state covariates\*[^13], state fixed
    effects, and year fixed effects, respectively.

-   SEs clustered by state, marginal effects.

Results
=======

Some descriptive comparisons

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/t2.png){width="0.9\\paperwidth"}

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/prior2rd1.png){width="0.95\\paperwidth"}

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/prior2rd2.png){width="0.95\\paperwidth"}

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/prior2rd3.png){width="0.95\\paperwidth"}

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/prior3rd3.png){width="0.95\\paperwidth"}

Results for MVC deaths

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/t3.png){width="0.95\\paperwidth"}

Results for proportion belted

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/t4.png){width="0.95\\paperwidth"}

Sensitivity analysis with subjective priors

![image](/Users/samharper/Dropbox/FARS/mvc-bayes/work/talk/rrplot-sens.png){width="0.9\\paperwidth"}

Compare to fully Bayesian analysis [^14]

-   Consistent with fully Bayesian estimates

-   Clustered standard errors more challenging in full Bayes

  --------------------------------------------- ---------------------------------- -------- --------
                                                 Posterior estimates from Poisson           
  Model                                                        Mean                 95% LL   95% UL
  *Non-informative priors for all parameters*                                               
  Semi-Bayes                                                  -0.023                -0.073   0.027
  Full Bayes\*                                                -0.016                -0.029   -0.003
  *$N(-1,0.05)$ for law, default for others*                                                
  Semi-Bayes                                                  -0.037                -0.092   0.019
  Full Bayes\*                                                -0.034                -0.047   -0.021
  --------------------------------------------- ---------------------------------- -------- --------

Discussion
==========

Interpretation

-   Given our empirical priors, model, assumptions, and data, we can
    revise our inference.

-   Impact on MVC deaths per billion VMT:

    -   We were 95% certain true effect was in the interval (-1.7, 0.9)

    -   Now we are 95% certain the true effect is in the interval
        (-0.89, 0.35).

-   Impact on proportion belted:

    -   We were 95% certain true effect was in the interval (0.03, 0.23)

    -   Now we are 95% certain the true effect is in the interval (0.04,
        0.07)

-   For both outcomes, likelihood gets more weight, updated evidence is
    toward the null.

Implications

-   MVC death rates still declining over this period.

![image](6_Users_samharper_Dropbox_work_research_projects_FARS_mvc-bayes_work_talk_fig1.png){height="0.8\\textheight"}

Conclusions

-   Incorporating new evidence suggests weaker impact of primary laws on
    death rates and proportion of deaths belted.

-   May imply other mechanisms contributing to declines in MVC death
    rates

    -   Improved road and vehicle technology;

    -   Traffic calming measures.

-   Possible that recent converts to seat belt use (due to law upgrades)
    are a subpopulation with different risks.

-   Incorporating prior evidence can help provide better estimates of
    future policy impacts.

Reproducible materials

-   Code and data on my OSF page (https://osf.io/em2y7/)

![image](7_Users_samharper_Dropbox_work_research_projects_FARS_mvc-bayes_work_talk_osf-pic.png){height="0.8\\textheight"}

Acknowledgements

-   No specific funding for this project.

-   Canadian Institutes for Health Research

-   Salary award from Fonds de recherche du Quebec Sante

-   Smarter Choices for Better Health Initiative, Erasmus University

Thank you!

sam.harper\@mcgill.ca![image](8_Users_samharper_Dropbox_work_research_project____2018-10-visit_kickoff_kickoff-talk_twitter.png)\@sbh4th

[^1]: Source: OECD (2018), Road accidents (indicator). doi:
    10.1787/2fe1b899-en (Accessed on 21 October 2018)

[^2]: Source: Insurance Institute for Highway Safety

[^3]: Pew Trusts, Stateline, April 28, 2017. http://bit.ly/2pFTFPp

[^4]: http://www.9news.com, Dec 8, 2016.

[^5]: https://www.aclu.org/report/racial-disparities-florida-safety-belt-law-enforcement

[^6]: \*Harper & Strumpf, *Am J Prev Med* 2017.

[^7]: Estimates from random effects meta-analysis.

[^8]: Hedlund et al. (2008). Estimates from random effects
    meta-analysis.

[^9]: Greenland (2006, 2007), Sullivan and Greenland (2013)

[^10]: Higgins & Spiegelhalter (2000); Greenland (2007,2008)

[^11]: \*NHTSA, *Primary Enforcement Saves Lives* (2006); CDC, *Motor
    Vehicle Prioritizing Interventions*.

[^12]: Meyer (1995); Angrist & Pischke (2009); Ryan et al. (2015)

[^13]: speed limit laws, graduated driver's license laws, BAC laws,
    alcohol consumption per capita, police officers per capita, state
    median income, police reported alcohol involved, and proportion of
    crash deaths on rural roads.

[^14]: \*Rstan model `bglm2` above, 4 chains, each with iter = 2000;
    warmup = 1000; thin = 1; total post-warmup samples = 4000)
