---
layout: post
title: Learning Basic Stats (p-value)
date: 2020-03-12 15:07 -0700
---
Today I spent a decent chunk of time learning about p-values and all the troubles it's caused in science.

Apparently it's a very common and easy practice to play around with your data/statistical analysis such that your results will produce a p-value of less than or equal to 0.05, which is the level at which papers often get accepted for publication. Some people are perhaps being intentionally misleading with the p-values, but others (and the scientific community at large) seems to be misinterpreting it.

Before all the readings, this was my fuzzy understanding of p-values: the probability that you would obtain the observed results if the null hypothesis were true. A low p-value means that it's very rare to observe the results we observed, if the null hypothesis were true. So we can conclude that the null hypothesis isn't true, and accept the alternate hypothesis, that so-and-so effect is real, knowing that the likelihood that we're wrong is p.

Unsurprisingly, my initial understanding was wrong. More specifically, I was wrong to make the jump from the definition of p-value to claim that we can 'accept the alternate hypothesis... knowing that the likelihood that we're wrong is p'. These are some of the common misinterpretations of p *[[source](http://www.dcscience.net/Sellke-Bayarri-Berger-calibration-of-P-2001.pdf)]*:
- As a direct frequentist error rate
- As the probability that the hypothesis is true in light of the data
- As a measure of the odds of the null hypothesis to the hypothesis

The reason why I got it wrong had a lot to do with something called the "Transposed conditional" -- where we incorrectly infer the probability of `P(A|B)` based only on `P(B|A)`. Example: The chance that it's raining when the sky is cloudy is 30%, `P(raining|cloudy) = 0.3`. But we can't then infer based on this claim that there's also a 30% chance that the sky is cloudy when it's raining `P(cloudy|raining) = 0.3`.

The p-value IS NOT the probability that your observations happened by purely random chance. It is the probability that your observations happened by random chance GIVEN the null hypothesis/a real effect, `p = P(observations|null-hypothesis)`. It is NOT the probability that there is a real effect, given the observations, `p != P(hypothesis|observations)`.

Working through a couple of different examples helped me understand this concept better *[[source](https://royalsocietypublishing.org/doi/full/10.1098/rsos.140216#d3e345)]*.
Let's say we're testing 1000 different drugs to see what works. Let's also say that, based on historical data, only about 10% of the drugs actually work. Now, one of your tests returns a p-value of 0.047, and you claim that you've discovered a statistically significant result. You think the p value means that there's only a 5% chance that the test is wrong (a false positive). But this is wrong. The chance that the test is wrong (a false positive) is actually much higher -- 36%. Why is this?

I find this chart pretty useful:
![chart]({{ site.baseurl }}/assets/pvalue.png)

You can see pretty clearly from this chart that the p values refers to false positive cases ONLY for the subset of cases where the null hypothesis is true (where there is no effect). We want to know the false positive likelihood for BOTH cases where the drugs work and don't work. We want to answer the question of: "I have a positive test here, what does it mean? How much should I trust this test?" And it is possible to do so in this case because we have a prior: we know that 10% of the drugs we test works.

Based on the prior, there are 100 cases where the drugs have a real effect, and 900 where they don't. Using the p-value, we know that there's a 0.047 chance that a no-effect case would test *positive*. That's `900 * 0.047 = 45` false positive cases.

For the true positive cases -- let's say there's a 80% chance of getting a true positive, and 20% of getting a false negative. That gives us 80 cases of true positives.

So the percentage of false positives over the total number of positives is actually `45 / (80 + 45) = 36%`. 36% is the likelihood of you getting the observed positive results totally due to random chance, whereas the p-value is just the likelihood of getting the observed positive results for the cases where the drugs don't work. 36% is much higher because it takes into account that there are way more cases where there is no real effect (null-hypothesis cases) than there are cases with a real effect. Of course, this also means that you can assume that there's a `1 - .36 = 64%` chance that the drug actually works based on a 'significant' positive result.

What this example demonstrates is that, if you concluded that the drug works based on the tests that yield `p<=0.05`, then you'll actually be wrong 36% of the time. The 36% here is also called the False Positive Risk (FPR) -- it takes into consideration ALL possible positive cases, not just the positive cases where the null hypothesis is true.

So these are the problems with p-values: they are easily misinterpreted and they can't tell us about what we *really* want to know, ie: what is the probability that our hypothesis is true given the evidence.

Many academics have weighed in on this issue and made suggestions for how the scientific community can overcome the p-value troubles, but it doesn't seem like there's clear consensus the solutions should be. One is to include the FPR value alongside the p-value, and to use the 'minimum' FPR value if no better historical data is available, which is 0.5 -- it is equally likely that there is and isn't a real effect. Another is just to be very transparent about the data and methods of the study -- allowing the scientific community at large to replicate and sort out the results.
