# Writing a term paper or thesis with quantitative methods: suggestions for a student guideline

Draft list of tips for a guideline covering term papers (Hausarbeit), BA theses and MA theses that use quantitative data. It draws on the course concept for Statistik I + II (PPDAC, the wording rules, the three challenges) and on the books digested for it (Spiegelhalter, *The Art of Statistics* and *The Art of Uncertainty*; Freedman/Pisani/Purves; Llaudet & Imai; Wheelan; Çetinkaya-Rundel & Hardin, *Introduction to Modern Statistics*). Items marked **[BA/MA]** apply mainly to theses; everything else applies to all three formats. Section 11 lists where in Spiegelhalter's two books, in Llaudet & Imai and in Çetinkaya-Rundel & Hardin the reasoning behind many tips can be read.

---

## 1. The question comes first

1. **Start from a sociological question, not from a data set or a method.** "What explains X?" or "How does X differ between groups?" comes before "I want to run a regression".
2. **Say what kind of question you are asking.** Is it a *description* (how common is X? how has it changed?), a *prediction*, or an *explanation* (does X cause Y)? Each kind needs a different design and allows different conclusions. The same regression can serve all three goals, but the goal decides how you read it and what counts as a good model: for a prediction, how well the model fits (R²) is central; for a causal question it is beside the point, and what matters is whether the compared groups are comparable. A good descriptive paper is better than a weak causal one.
3. **Use the PPDAC cycle as your plan:** Problem (the question), Plan (what to measure, which data, which comparison), Data (getting and cleaning them), Analysis (looking, then modelling), Conclusion (what you found, how far it carries, what new question it raises). Most weak papers skip from Problem straight to Analysis.
4. **Make the question answerable with the data you can actually get.** Check data availability before you commit to a topic. Some questions cannot be answered by any data set you can get. Why something changed over time is the typical case: a trend alone does not tell you its cause.
5. **Derive hypotheses from theory and state them before you look at the results.** Say which direction you expect and why. Write the hypotheses down early, with a date (for a thesis: in the Exposé).
6. **Know whether your study is confirmatory or exploratory, and say so.** A confirmatory analysis tests hypotheses fixed in advance. An exploratory analysis looks around and generates new hypotheses. Both are legitimate. The problem is exploring and then presenting the result as if it had been predicted all along ("hypothesising after the results are known").
7. **Keep the scope small.** One clear question answered well beats five questions answered superficially. Term papers in particular should answer one question with one main analysis.

## 2. Data: know what you have

8. **Describe where the data come from:** who collected them, when, how (survey mode, sampling), and who is in them. Cite the data set properly (with DOI and version where available, e.g. ESS, ALLBUS, SOEP).
9. **Ask "who is in the data, and who is missing?"** Go through the chain from your numbers to your conclusion step by step:
    - *Recorded answers to the people in the sample:* did respondents answer honestly and accurately?
    - *Sample to the population that could have been sampled:* how was the sample drawn, and how many responded?
    - *That population to the one you want to talk about:* who could never be in the data (people in institutions, people without internet, non-German speakers)?

    A convenience sample (e.g. a class survey or an online survey among friends) can be useful, but it does not support claims about a whole population, and no statistical method can fully repair that afterwards. If you draw your own sample (which classes, streets or respondents), let a random mechanism decide, not your judgement: people are poor at choosing at random and tend to pick cases that are easy to reach or look typical. Watch out in particular for selection on the outcome: if only successful cases make it into the data (firms that survived, students who graduated, projects that were completed), you cannot learn what made them successful, because the failures that did the same things are missing.
10. **A large sample does not cure a biased one.** Thousands of respondents from a skewed sampling frame or with a very low response rate still give a skewed picture, only with more confidence. Size reduces chance error, not bias.
11. **Ask "what exactly was measured?"** Quote the exact question wording and answer scale of your key variables, in the text or the appendix. Discuss whether the indicator captures your concept (validity) and how reliably. Wording, answer options and the order of questions can change answers considerably. In one British survey, about half supported "giving 16- and 17-year-olds the right to vote", but only about a third supported "reducing the voting age to 16". If an indicator stands in for something you cannot observe directly (night-time light seen from satellites for economic activity, a single item for "trust"), show how closely the two are known to go together. If your data come from a register or official statistics, ask what gets recorded: police statistics count crimes that are reported and recorded, which is not the same as crime.
12. **Check the data for plausibility before you trust them.** Look for heaping on round numbers, impossible values, and answers that cannot all be true together (for example, if men and women in a closed population report different average numbers of partners, someone is misreporting). Such patterns tell you something about measurement quality, and they belong in the discussion. Where an answer is socially desirable, compare with an outside figure if one exists: in US election studies, more than 70 % of respondents say they voted, while official turnout is around 60 %. Also check how each variable is stored: numbers stored as text, and codes stored as numbers (postcodes, party codes, education levels 1-5), which software treats as quantities unless you declare them as categories.
13. **Treat survey weights deliberately.** Check the data documentation for whether and which weights to use, and state your choice.
14. **Document every data-cleaning step:** case selection, recoding, handling of missing values ("weiß nicht", "keine Angabe"), constructed indices. Report how many cases you lose at each step (a short case-flow table works well).
15. **Drop missing values only for the variables you actually use, and check what dropping does.** Many commands (e.g. `na.omit()` in R) delete every case with a gap in *any* variable of the data set, including variables you never use. Compare your key figures before and after case selection. In a large British pre-referendum survey, the share supporting Leave was 48.8 % among those who had decided, and 47.2 % once everyone without an education answer had also been dropped: a cleaning decision moved the estimate by more than twice its margin of error. If many values are missing, say who is missing and in which direction this could bias your result; **[MA]** consider multiple imputation.
16. **Do not quietly delete outliers or inconvenient cases.** Exclude cases only for a stated reason, and say how results change if they are kept. A single mistyped value can change a mean, a standard deviation or a correlation considerably.

## 3. Design and analysis

17. **Look at your data before you model them.** Univariate distributions, then bivariate relationships, then multivariate models. Many errors (coding mistakes, wrong missing codes like 99, skewed distributions) show up in a simple histogram or table. Very different patterns can share the same mean, standard deviation and correlation, and only a plot shows the difference.
18. **Choose summaries that fit the distribution.** Median for the typical case in skewed variables such as income (the mean is still the right figure when totals matter, such as tax revenue or costs per head), shares for categorical variables, and say "percentage points" for differences between percentages. Report the spread as well as the centre (interquartile range or standard deviation), and check whether a few extreme values drive the result. If your units differ in size (districts, countries, schools), the plain average of their values is not the average per person: a district of 5,000 counts as much as one of 500,000. Weight by population if your question is about people.
19. **Choose the method because it fits the question and the data, not because it looks sophisticated.** A clearly explained cross-tab or comparison of means can be the right answer.
20. **Choose control variables by reasoning, not by availability.** For each control, ask: could it affect both my explanatory variable and my outcome (confounder)? Do *not* control for variables that lie on the causal path (mediators) or that are consequences of the outcome, unless that is exactly your question. What you hold constant decides which question you answer. Adjusting can make an association larger as well as smaller: a confounder that pushes the outcome in the opposite direction hides part of the relationship until you hold it constant. Remember that adjusting for observed variables never rules out confounding by unobserved ones.
21. **Check that the groups you compare actually overlap on your control variables.** Cross-tabulate your explanatory variable against each important control before you adjust. If, say, almost everyone near a border receives foreign TV and almost no one far from it does, the adjusted comparison rests on the few cases that break the pattern; in one study this was 33 of 358 respondents. Report how many cases carry the comparison, and say so if the model has to extrapolate into combinations that hardly occur in the data.
22. **Do not throw in every available variable** and see what comes out significant. That produces chance findings. The same holds for automated stepwise selection, which adds and drops variables by p-values or fit statistics: at best it serves prediction, and the p-values of the model it ends with are no longer valid.
23. **Every additional test raises the chance of a false discovery.** If nothing is going on, each test at the 5 % level still has a 1 in 20 chance of coming out "significant". With ten tests, the chance of at least one false positive is about 40 %. This applies to subgroups, alternative outcomes and alternative codings alike. Say how many tests you ran. If you run many, use a correction (e.g. Bonferroni) or treat the results as exploratory. The same holds for patterns you noticed first and tested afterwards: if a cluster or a difference caught your eye in the data, a test on the same data says little, because a different pattern elsewhere would have struck you just as much. Treat it as a hypothesis for new data.
24. **Compare subgroups directly.** "Significant for women, not significant for men" does not show that the relationship differs between women and men. The difference between "significant" and "not significant" is often not itself significant. Test the difference itself, e.g. with an interaction term.
25. **Check whether your observations are independent.** Standard errors and p-values assume that each case adds independent information. Pupils in the same school, people in the same household, repeated answers from the same person, or respondents interviewed by the same interviewer are more alike than randomly chosen cases. Treating them as independent makes intervals too narrow and p-values too small. Use clustered standard errors or a multilevel model, and say which. If the same units are measured twice (before and after, both partners of a couple, two exams per student), analyse the paired differences instead of comparing two groups as if they were independent; pairing usually makes the comparison much more precise. Multiplying probabilities as if events were independent is a classic error with real consequences: in the British Sally Clark case, two cot deaths in one family were put at 1 in 73 million, ignoring that such deaths run in families, and a mother was wrongly convicted.
26. **Plan the analysis before running it, and stick to the plan.** If you change course, say so. Small decisions taken after seeing the data (when to stop collecting, which cases to exclude, which controls to add, how to group a variable) all push results towards significance, even without bad intent. Do not try many specifications and report only the one that "works". Use two-sided tests unless a strong reason for one direction was stated before seeing the data: switching to a one-sided test because the data point that way doubles the rate of false positives. **[MA]** Consider writing down your analysis plan in advance, ideally pre-registered (e.g. on the Open Science Framework).
27. **Check the assumptions of your model in pictures:** residual plots, linearity, influential cases, collinearity between explanatory variables. Not all assumptions matter equally. Linearity and independent observations matter most. Normally distributed residuals matter little in larger samples, so a formal normality test adds little. Strongly correlated explanatory variables make single coefficients and their p-values hard to interpret, but do not harm predictions. For a binary outcome, check that predicted values stay between 0 and 1, or use a model that guarantees it.
28. **Run robustness checks** for decisions that could have gone another way (different coding, different sample, different model), and report them, at least in the appendix. How much such decisions can matter was shown when 246 biologists analysed the same data sets: their different but reasonable choices led to widely different conclusions. **[BA/MA]**
29. **[MA] Where the standard formulas are doubtful, consider the bootstrap (for intervals) or a permutation test (for experiments).** Resampling your own data with replacement gives standard errors and intervals without assuming a particular distribution; shuffling the group labels tests a difference between randomly assigned groups. Compare the result with the conventional interval. Neither is a cure for a small or unrepresentative sample: the bootstrap can only be as good as the sample it resamples, it works poorly with very few cases or very few events, and with clustered data whole clusters must be resampled.
30. **[MA] If your question is a prediction, compare your model with a naive baseline.** Report how much better it predicts than simply using the overall average or the most common category, ideally on data not used to fit the model. A model that classifies 70 % of cases correctly is unimpressive if 65 % fall into one category anyway. When one category is rare, overall accuracy also hides how the rare cases fare: report separately how many of the actual cases in each category the model gets right, and say which cut-off turned predicted probabilities into categories.

## 4. Reporting results

31. **Report the size of a result, not only its significance.** Give the estimate in original units (euros, years, percentage points) and say whether the difference matters substantively. With very large samples, tiny and unimportant differences become significant. Likewise, a low R² is normal for data on individuals, since most variation between people is not explained by any measured factor; it does not make an association unimportant, and a high R² does not make it causal.
32. **Write each result sentence so that it can stand on its own.** It names the comparison (who against whom), the direction, the size *with its unit*, whether it is an average, and what kind of claim it is (association or effect, and on which assumption). The unit follows from the variable: the mean of a 0/1 variable is a share (read it as percent); the difference between two shares, and the coefficient of a 0/1 outcome in a linear model, is in percentage points; a coefficient of a numeric outcome is in that outcome's unit; in models with logged variables, coefficients read approximately as percent changes. Example: "Among respondents without a school-leaving qualification, the share intending to vote Leave was 73 %; among those with a postgraduate degree it was 25 %, a difference of 48 percentage points (survey data, association only)."
33. **Report risks and shares in absolute as well as relative terms.** "18 % higher risk" can mean a rise from 6 to 7 cases in 100. Give the baseline. Odds ratios from logistic regression are not relative risks and exaggerate the difference when the outcome is common. Translate them into predicted probabilities or percentage-point differences. Relative measures still have their place: they are the right summary when the baseline differs between groups, places or periods, as with the efficacy of a vaccine. Report both, and let the reader see the baseline.
34. **Say what each number refers to.** Compare rates, not totals, when groups differ in size: 300 cases among 1,000 people is a lower rate than 200 among 500. A percentage needs its base and, for rates, its time span: "91 % effective" for a contraceptive means that about 9 in 100 users become pregnant within a year. Check that indicators with the same name are measured the same way across your cases, sources and years. Money is the obvious trap: GDP or income in national currencies, or in prices of different years, cannot be compared or pooled until converted to a common unit (e.g. constant euros or purchasing-power parities). Likewise, life expectancy can be calculated from current death rates or from expected future ones, and the two differ by several years. When comparing risks or shares, use a fixed denominator ("7 in 1,000" against "12 in 1,000"), not "1 in 143" against "1 in 83"; about a quarter of people cannot say which of 1 in 10, 1 in 100 and 1 in 1,000 is the largest.
35. **Be aware of framing.** "95 % survive" and "5 % die" state the same fact and leave different impressions. Choose a neutral presentation or give both.
36. **Always report uncertainty:** standard errors or confidence intervals, plus the number of cases (n) for every analysis.
37. **A confidence interval is a lower bound on your uncertainty.** It covers chance error from sampling only. Nonresponse, measurement error and a flawed sampling frame are not included, and they rarely shrink with a larger sample. Discuss them separately. Uncertainty about the choice of model is not in the interval either: different reasonable models of the same data can give intervals that do not even overlap. Even in physics, published values for the speed of light carried error margins for decades that did not include today's value.
38. **"Significant" is not "important", and "not significant" is not "no effect".** A non-significant result may mean the sample was too small to detect it. Report what range of values your data are compatible with. In German, *signifikant* also means "important" in everyday speech; write *statistisch signifikant* in full, or say that a result is distinguishable from zero. One recent textbook (Çetinkaya-Rundel & Hardin) speaks of "statistically discernible" for this reason.
39. **Interpret confidence intervals correctly.** Not "the true value lies in this interval with 95 % probability", but: under repeated sampling, 95 % of intervals built this way would contain the true value, *assuming the sample differs from the population only by chance*. A useful shorter reading: the interval holds the values that are compatible with your data at the chosen level (sometimes called a compatibility interval). The interval is about a population value such as a mean, not about individuals: a 95 % interval for average income does not contain the incomes of 95 % of people.
40. **Interpret p-values correctly.** A p-value is the probability of a result at least this extreme *if* the null hypothesis, and all other assumptions of the model, were true. It is not the probability that the hypothesis is true or that the result arose "by chance". A p-value near 0.05 is only weak evidence; report the exact value rather than only stars or "p < 0.05".
41. **Say what inference means if you have all the units.** If your data cover every case (all EU countries, all German districts, all elections), there is no sampling. Standard errors then refer to an assumed process that could have produced other outcomes, not to a sample. Say so, or drop the inference and describe. More generally, say where the chance in your analysis comes from: from a random sample (then the interval speaks about the population sampled), from random assignment in an experiment (then it speaks about the people in the experiment; generalising beyond them needs a separate argument), or from a model you assume. A significant effect in an experiment with volunteers or selected schools is not yet a result about all pupils. A two-by-two table helps: was the sample random, and was the explanatory variable randomly assigned? Only the first supports generalising, only the second supports a causal claim, and few studies have both.
42. **Read regression coefficients as differences between cases**, e.g. "people with one additional year of education report on average 0.3 points higher trust, holding age and gender constant". This compares different people. It does not say what would happen if one person gained a year of education. Avoid "effect" and causal verbs ("beeinflusst", "führt zu", "bewirkt") unless your design supports a causal claim.
43. **Report all tests you ran for your hypotheses, including those that did not confirm them.** Unexpected or null results are results.
44. **Read conditional shares in the right direction.** The share of X among Y is not the share of Y among X. In the UK in mid-2021, most people who died of Covid had been vaccinated, simply because almost all older people were vaccinated; the risk of dying was still far lower with the vaccine. In a cross-tab, decide within which variable you percentage (usually within the categories of the explanatory variable, so that each group you compare adds up to 100 %), say so in the table, and phrase the sentence accordingly ("Among women, 40 % …").
45. **Make tables readable:** clear variable labels (not `v231_rec`), units, reference category for categorical variables, n, and a note on what the numbers are (coefficients, standard errors, etc.). Leave out what nobody needs.

## 5. Figures

46. **Every figure answers one question.** Its title or caption states the finding.
47. **Show the data and their spread, not only means.** Prefer dot plots, histograms, boxplots with points over bare bar charts of means. When you compare the distributions of groups of very different size, show shares (percent or density), not counts; otherwise the larger group dominates the picture. With many cases or few distinct values, points overlap: use transparency or slight jitter. Use bar charts instead of pie charts, and never 3D effects. Order categories by meaning: answers on a scale (agree … disagree) in the order of the scale, other categories by size, never alphabetically just because the software does so.
48. **Use honest scales:** bars start at zero; no dual axes; log scales only when ratios matter, and labelled as such. If all values lie in a narrow range (e.g. 86-99 %), bars from zero hide the differences and truncated bars exaggerate them. Use a dot plot with a suitable axis instead.
49. **Label directly, name the source and the sample, show uncertainty** (error bars, bands) and say what the bars mean (SE or 95 % CI). Error bars suggest a sharp edge, as if every value inside were equally plausible and every value outside impossible; shaded bands or plots of the whole distribution avoid that impression.
50. **Colour with a purpose**, readable for colour-blind readers and in black-and-white print. For ordered categories, use one colour running from light to dark rather than unrelated colours. Text must be legible.
51. **Consider turning regression tables into coefficient plots** in the main text, with the full table in the appendix.
52. **For small or rare groups, show the noise.** Rates for small units (districts, schools, small subgroups) scatter more by chance. A plot of the rate against group size, with the range expected by chance, prevents reading chance extremes as findings. The same applies to rankings: when intervals overlap widely, the order of places is largely chance.

## 6. Interpretation and conclusion

53. **Finding first, limits second.** First state what you found, then how far it carries.
54. **Check plausibility.** Does the size of your result fit what is known? An effect that is much larger than in earlier research, especially from a small sample, is more often an error or chance than a discovery. Check your code before you check your theory. If a result looks very surprising, count the opportunities: with many variables, subgroups and years, some striking pattern is almost bound to appear somewhere.
55. **Say how good the evidence is, not only how precise the estimate is.** A narrow interval from one convenience sample is weaker evidence than a wider one confirmed in several data sets. Give an overall judgement (for example strong, moderate or weak) with reasons: the quality of the data, how many studies agree, how directly the data address your question. Medicine (GRADE), the IPCC and the Education Endowment Foundation use ratings of this kind.
56. **Match the strength of your claims to your design.** Observational data support statements about associations. Causal language needs a design that rules out alternatives (experiment, natural experiment, panel data with appropriate methods), and even then state the assumptions.
57. **If you argue towards a cause with observational data, use explicit criteria.** How strong is the association, and could confounding plausibly explain all of it? Does the cause come before the effect? Is there a dose-response pattern? Is there a plausible mechanism? Do other studies, with other data and designs, find the same? These are the questions Bradford Hill used for smoking and lung cancer.
58. **Discuss the three classic challenges explicitly:**
    - *Generalising:* to which population do the results apply? (external validity)
    - *Causes:* what else could explain the association (confounding, reverse causation, selection)? (internal validity) The two often pull against each other: an experiment with volunteers is strong on causes and weak on generalising; a large population survey the other way round. Say where your design stands on both.
    - *Measurement:* how well do the indicators capture the concepts?
59. **Watch for regression to the mean.** If cases were selected for extreme values at one point (worst schools, highest unemployment, lowest trust), they will on average be less extreme next time, with or without any intervention. Do not read that change as an effect.
60. **Cross-sectional age differences are not changes over the life course.** Older and younger respondents differ by cohort and by who has survived, not only by age.
61. **Data about groups support statements about groups.** If your units are countries, districts or schools, your results describe those units. A strong correlation between the share of graduates in a district and the district's vote does not tell you how strongly education and voting go together among individuals; correlations between averages are usually much stronger than between people, and can even differ in sign (ecological fallacy). If your question is about individuals, use individual data, or say clearly what the aggregate data can and cannot show.
62. **Do not generalise beyond your data**, neither to other populations nor beyond the range of observed values (extrapolation). This includes the intercept: it is the predicted value when every explanatory variable is zero, which is often nonsense (an income of zero, an age of zero) and then not worth interpreting. **[MA]** If you carry a trend forward, call it a projection under stated assumptions ("if the trend of the last ten years continues …"), not a prediction.
63. **Tie the results back to theory and to previous research.** Where do they agree, where not, and why might that be?
64. **Name limitations specifically**, and say in which direction they would likely bias your results. A generic "the sample could be bigger" adds nothing. A useful order for the conclusion: what we now know, what we still do not know, and what data or design would settle it.
65. **Avoid both overclaiming and reflexive self-dismissal.** A careful finding within stated limits is a contribution. A balanced presentation is also more convincing: in an experiment with over 1,000 people, those sceptical of a message rated a balanced version, with pros and cons, as more trustworthy than a persuasive one.

## 7. Reproducibility and research practice

66. **Do the analysis in a script (R, Stata), not by clicking.** Every number in the paper should come from the script. A spreadsheet error in an influential economics paper on public debt (Reinhart and Rogoff, 2010) left out five countries and was found only when a student tried to reproduce the analysis. A script makes such errors findable.
67. **Keep the raw data untouched.** Work on a copy; let the script do all recoding.
68. **Comment the code and keep it organised:** data preparation, descriptives, models, figures. Make sure it runs from top to bottom on a fresh start. If you use anything random (bootstrap, simulation, multiple imputation, random subsamples), set a seed at the top of the script (in R: `set.seed()`) and report it, so that every number can be reproduced exactly.
69. **Hand in (or make available) the code** with the paper, as an appendix or repository, unless the data licence forbids sharing the data. **[BA/MA]** Required in any case.
70. **Report software and package versions** in a footnote or appendix.
71. **Respect data protection and licences.** Do not pass on data you are not allowed to share; anonymise your own survey data; describe consent for own data collection.
72. **Cite methods sources as well as substantive literature** (textbook or methods paper for each non-standard technique).
73. **Be transparent about tools,** including AI assistance, as required by the examination rules. AI tools state true and false claims with the same confidence; check every number, citation and code line they produce.

## 8. Structure and writing

74. **Use a clear structure:** introduction (question and relevance), theory and hypotheses, data and methods, results, discussion, conclusion. Keep results and interpretation recognisably apart.
75. **The methods section should let a reader repeat the analysis:** data, sample, variables (with operationalisation), method, and key decisions.
76. **Lead each results paragraph with the finding**, then the evidence ("Women report lower trust than men (Table 2)..."). Do not narrate tables cell by cell.
77. **Explain every number you report** and every table and figure you include; refer to each in the text.
78. **Write for an intelligent reader who is not a statistician.** Define technical terms once, round sensibly (two meaningful digits are usually enough), and avoid false precision. Precision beyond what the data support looks scientific but is not: a published accident risk of "once in 15,397,000 years" claims an accuracy that no model can deliver.
79. **Use numbers, not only words, for probabilities and frequencies.** Readers turn words like "likely", "rare" or "common" into very different numbers. In an international study the typical reading of "likely" was 60 %, and one reader in ten put it below 25 % or above 90 %. If you use such words, give the number alongside ("likely, about 70 %").
80. **Title, abstract and conclusion must not claim more than the results.** Exaggeration usually enters there, not in the results section: a causal verb in the title, a relative risk without a baseline, a subgroup result presented as the main finding.
81. **Put detailed output in the appendix**, not in the main text.

## 9. Differences between formats (suggestion)

| | Term paper | BA thesis | MA thesis |
|---|---|---|---|
| Question | One narrow question | One question with sub-questions | Question positioned in a research debate |
| Data | Existing data set, often given | Existing data, own choice | Existing or own data; justification of choice |
| Analysis | Descriptives plus one well-explained model or comparison | Descriptives, main model, basic robustness | Multiple models, robustness checks, assumptions discussed |
| Causality | Associations; discuss alternative explanations | Associations; discussion of confounding | Causal design possible, with assumptions made explicit |
| Confirmatory or exploratory | Say which | Hypotheses fixed in the Exposé | Analysis plan written down in advance; pre-registration possible |
| Code | Recommended | Required | Required, fully reproducible |

## 10. Checklist before submission

- [ ] Research question and hypotheses stated before the results; exploratory parts labelled as such
- [ ] Data source cited; population, sample and response described; no selection on the outcome
- [ ] Wording and coding of key variables documented; codes declared as categories, not used as numbers
- [ ] Case selection and missing values documented (with n at each step); missing values dropped only for the variables used, and the effect of dropping checked
- [ ] Every analysis reports n, estimate, and uncertainty
- [ ] Sizes interpreted in substantive units, not only significance; risks with a baseline, absolute and relative
- [ ] Each result sentence names comparison, direction, size with unit (percent or percentage points), and the kind of claim
- [ ] Overlap of compared groups on the controls checked; number of cases that carry the comparison stated
- [ ] Every percentage has its base (and time span); cross-tabs percentaged in the direction the question needs
- [ ] Number of tests reported; subgroup differences tested directly; tests two-sided unless a direction was fixed in advance
- [ ] Clustered data (schools, households, countries, repeated measures) handled in the standard errors; paired data analysed as pairs
- [ ] No causal verbs for observational associations; aggregate data not read as statements about individuals
- [ ] Confidence intervals and p-values worded correctly; non-sampling error and model choice discussed
- [ ] Overall strength of the evidence stated, with reasons
- [ ] Every table and figure labelled, sourced, and discussed in the text; categories in a meaningful order
- [ ] Limitations specific, with the direction of possible bias
- [ ] Title and abstract claim no more than the results; no false precision, no vague probability words without numbers
- [ ] Code runs from start to finish and reproduces every number (seed set where anything is random)
- [ ] Results that did not support the hypotheses are reported
- [ ] Final test: go through Spiegelhalter's ten questions for a statistical claim (*The Art of Statistics*, ch. 13) with your own paper as the claim. How trustworthy are the numbers, the source, the interpretation?

## 11. Further reading

The reasoning behind many tips is explained, with examples, in two books by David Spiegelhalter, in Llaudet & Imai and in Çetinkaya-Rundel & Hardin. Chapter numbers are given because page numbers differ between editions.

**The Art of Statistics (2019).** German edition: *Die Kunst der Statistik* (Redline 2020); chapter numbers are the same in both.

| Tips | Topic | Chapter |
|---|---|---|
| 3 | The PPDAC cycle | Introduction |
| 9-12 | From sample to population; question wording; two sources, two answers | 3 |
| 16-18 | Mean, median, spread; plotting before summarising | 2 |
| 20, 56-57, 60 | Confounding, reverse causation, designs, Bradford Hill criteria | 4 |
| 27, 42, 59 | Regression, interpreting coefficients, regression to the mean | 5 |
| 29 | Bootstrap | 7 |
| 37, 39, 41, 52 | Confidence intervals, margins of error, funnel plots, inference with complete data | 9 |
| 23-24, 38, 40 | Tests, multiple testing, what p-values do and do not say | 10 |
| 6, 26, 54, 66, 80 | Questionable research practices, replication, exaggeration in reporting | 12-13 |
| 33-35, 48 | Absolute and relative risk, framing, bar charts | 1 |

**The Art of Uncertainty (2024).** Less about data analysis, more about chance, probability and how to say how sure you are.

| Tips | Topic | Chapter |
|---|---|---|
| 79 | Words versus numbers for probability | 2 |
| 23, 54 | Coincidences, counting the opportunities, patterns found after looking | 4 |
| 25 | Independence assumptions and misused probabilities in court (Sally Clark) | 10 |
| 52 | Luck in league tables and rankings | 5 |
| 31, 68 | The "hidden half" of unexplained variation; random numbers and seeds | 6 |
| 44 | Base rates and conditional probabilities read the wrong way round | 7 |
| 28, 37, 39-40 | Margins of error that are too small, model choice, many analysts, P-values and compatibility intervals | 8 |
| 55 | Rating the quality of evidence | 9 |
| 30, 62 | Judging predictions against a baseline; projections versus predictions | 11 |
| 78 | False precision | 12 |
| 33-35, 49, 64-65 | Absolute and relative risk, what a number refers to, framing, showing uncertainty in charts, saying what we do not know, balanced communication | 14 |
| 9, 73 | Survivorship bias; AI tools and overconfidence | 16 |

**Llaudet & Imai, *Data Analysis for Social Science: A Friendly and Practical Introduction* (Princeton University Press, 2023).** A gentle introduction built on four published social-science studies (class size, Brexit, night-time light as a measure of growth, Russian TV in Ukraine), with R code. Two cautions: the book reads regression coefficients causally once the authors' chosen controls are included, and sometimes says the true value "is likely" inside a confidence interval. Use the wording of tips 42 and 39 instead.

| Tips | Topic | Chapter |
|---|---|---|
| 2 | Measure, predict, explain; how the goal changes the reading of a regression | 1, 5 (§6) |
| 9-12 | Random sampling and four ways it fails; misreporting | 3 (§2) |
| 14-15 | Missing values and what dropping them does | 3 (§4.1), 7 (§2.1) |
| 17-18, 47 | Histograms, density histograms, mean, median, standard deviation | 3 (§4) |
| 20-21 | Confounders, mechanisms, post-treatment variables, overlap | 5 (§2-3) |
| 31-32, 42 | Reading means, differences and coefficients in the right unit; percent vs percentage points; log models | 1 (§8), 2 (§5), 4 |
| 36-41 | Sampling distributions, confidence intervals, tests, statistical vs substantive significance | 6-7 |
| 34 | Variables in different units across countries | 4 (§4) |
| 45 | Reading and laying out regression tables | 7 (§3.2) |
| 56, 58 | Causal claims; internal and external validity; experiments vs observational data | 2, 5 (§5) |
| 61 | Group-level and individual-level data | 3 (§5) |
| 62 | Extrapolation and the intercept | 4 (§4.1) |

**Çetinkaya-Rundel & Hardin, *Introduction to Modern Statistics* (2nd ed., OpenIntro 2024).** Free to read online and to download (openintro.org/book/ims), with free self-paced R tutorials that run in the browser. Strong on study design, on charts, and on intervals and tests by simulation (bootstrap and shuffling) before formulas; examples are mostly American. Two cautions: it writes "statistically discernible" for "significant" (fine, but stay consistent with your own field's usage, see tip 38), and its quick reading of intervals ("we are 95 % confident that …") is shorter than the wording of tip 39. It also presents stepwise model selection; see tip 22 before using it.

| Tips | Topic | Chapter |
|---|---|---|
| 9, 41, 56, 58 | Sampling designs, non-response, convenience samples; random sampling against random assignment (Fig. 2.8) | 2 |
| 12, 17 | Tidy data, variable types, a first look at a new data set | 1 (§1.2), 3 (§3.1) |
| 18, 34 | Mean or median, robust statistics, box plots, log transformation; rates and per-person averages | 5 |
| 44, 47 | Two categorical variables: row and column proportions; stacked, 100 % and side-by-side bars | 4 |
| 46-50 | Rules for clear charts, including the order of categories and colour | 6 |
| 16, 27, 62 | Least squares, residuals, outliers and leverage, extrapolation | 7 |
| 20, 22 | Multiple regression; why coefficients change when variables are added; stepwise selection | 8, 25 (§25.2) |
| 29, 39 | Bootstrap intervals; what 95 % means | 12, 13 (§13.6), 17 (§17.2) |
| 26, 38, 40 | Tests by shuffling, p-values, the two kinds of error, one- and two-sided tests | 11, 14 |
| 23 | Data snooping and multiple comparisons | 22 |
| 25 | Paired data | 21 |
| 27 | Conditions for inference in regression, and which matter most | 24 (§24.6) |
| 30 | Accuracy of classifications; checking predictions on held-out data (cross-validation) | 9, 25 (§25.3), 26 |
