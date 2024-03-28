# 0 Prerequsites
A [link](https://github.com/ethanwang04/Stat_111) to my statistical inference coursework. All assignments were completed using rmd.

More up to date classwork can be found [here](https://github.com/ethanwang04/Classes_S24), including coursework with capital markets.

# 1 Easy
Install went easily for actually installing the packages in R. I had to learn how to use GitHub to pull the files from the repos to access the Vingettes. There were some issues learning the frameworks of github, but those were quickly learned and ironed out.

# 2 Intermediate

Not shown here as per the instructions. 

# 3 Hard

The only vignette that worked for me was Commodities-long-run.rmd. I will present my test in two sections: Interpretation of the statistical estimates and repetitive code that can be condenced.

## Statistical estimates

Here are a few things I noticed when I was reading through the Vignette

- Discrepancy between arithmatic and geometric returns are higher when volitility is higher. Intuitively, this makes sense as geometric returns would go to zero as volititlity increases while arithmetic mean would remain relatively unchanged
- Regression over the entire time period gave alpha of 0.00728 for equal weighted and 0.00351 for long-short. Positive alpha shows that our commodities prices are outpreforming what the model would predict
- Interestingly, both of the above strategies have positive factor beta with inflation state, showing that commodities preform better when inflation is high.
- R-squared values are quite low for each of the regressions, so extrapolation is pretty much out of the question
- Despite low R-squared value, we have a majority of F-statistics being statistically significant
- We have MoM being most statistically significant in the long-short strategy, but that effect wears off when we examine long-horizon
- Interestingly, it seems like none of the investment strategies are statistically significant when we examine the long horizon
  

## Repetitive code
Throughout the vignette, there appeared to be many places where similar code was written (e.g. preparing datasets, passing parameters into functions, etc.). However, this is difficult to create a new function in the package to handle as this is very specific to the usecase and the vignette itself rather than an overarching issue. The only universal function that could help is a function to print the results of the multivariate regressions (maybe bake this into LmHorizon()). This already seems to be built into fitTsfm, so a similar function could help for LmHorizon().
