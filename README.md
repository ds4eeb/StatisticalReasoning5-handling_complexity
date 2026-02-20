Activity 13: Statistical reasoning 5: handling complexity
================

Welcome! This is the fifth statistical reasoning activity. The goals of
this activity are to understand how to implement and interpret
*interactive* models (of multiple regression).

------------------------------------------------------------------------

You will submit one output for this activity:

1.  A **PDF** of a rendered Quarto document with all of your R code.
    Please create a new Quarto document (e.g. don’t use this
    `README.qmd`) and include all of the code that appears in this
    document, your own code, and **answers to all of the questions** in
    the “Q#” sections. Submit this PDF through Gradescope.

A reminder: **Please label the code** in your final submission in two
ways:

1.  denote your answers to each question using headers that correspond
    to the question you’re answering, and
2.  thoroughly “comment” your code: remember, this means annotating your
    code directly by typing descriptions of what each line does after a
    `#`. This will help future you!

------------------------------------------------------------------------

# 1. Interactions

Back when we introduced multiple regression in “Activity 10: Statistical
Reasoning 2 - multiple regression” we looked at the Palmer Penguins
dataset. Included in that activity was this paragraph:

> **This is an additive model**, which means that that the effect of one
> predictor is treated as independent of other predictors. Rephrased,
> this means that this model structure assumes that the effect of bill
> length on bill depth *will not differ between species*. If we think of
> this graphically, it means that this model forces each species to have
> the exact same slope. In our example, this seems like a fine
> assumption: in the graph above, notice that the slopes that
> geom_smooth() puts on the graph are basically parallel (parallel lines
> = equal slopes). If we feel that the slope should actually be
> different for each species, then we would use an *interactive model*
> instead of an *additive model*, but don’t worry about that - we’ll get
> to that later in the quarter!

Guess what? It’s later in the quarter!

------------------------------------------------------------------------

Interactions occur when one the value of one predictor variable
influences the effect of a second predictor on the response. Now, one
predictor is *conditional* on another. For instance, imagine that for
one species of penguin, increasing body mass leads to longer bills,
while for a second species, increasing body mass leads to smaller bills.
What is the effect of body mass on bill length? In this example, it’s
*conditional*: if species A, then it’s positive, but if species B, it’s
negative. Lots of ecology is like this: “It depends!”

------------------------------------------------------------------------

### Q1.1 Describe the interaction in the comic

In this XKCD comic below, `productivity` is a function of the
interaction between `power outage` (pre vs post outage) and the
`reliance on internet for work`. In 1-2 sentences, describe the effect
of how the power outage interacts with the reliance on internet on
productivity.

![XKCD service outage](pictures/xkcd-3170-service-outage.png)

==== ANSWER

A power outage increases the productivity of people who do not rely on
internet, but decreases the productivity of people who do rely on
internet (or similar - really there’s an effect on the intercept vs an
effect on the slope, but that’s not important here; it’s more of a vibes
question)

==== END ANSWER

------------------------------------------------------------------------

### Q1.2 What additional variable would lead to an interaction?

For each of the causal relationships below, name a hypothetical third
variable that would lead to an interaction effect and describe what the
effect would be. For instance, what would cause the effect of e.g. yeast
on the rate of bread rising to increase/decrease?

- Bread dough rises because of yeast.
- Education leads to higher income.
- Gasoline makes a car go.

==== ANSWER - Bread dough rises because of yeast. Temperature would
increase the effect of yeast on bread - Education leads to higher
income. Parental income would make the effect of education on income
stronger - Gasoline makes a car go. Engine strength would make a car if
gas \> 0, but wouldn’t be effective if gas = 0 ==== END ANSWER

------------------------------------------------------------------------

------------------------------------------------------------------------

### Render to PDF

When you have finished, remember to pull, stage, commit, and push with
GitHub:

- Pull to check for updates to the remote branch
- Stage your edits (after saving your document!) by checking the
  documents you’d like to push
- Commit your changes with a commit message
- Push your changes to the remote branch

Then submit the well-labeled PDF on Gradescope. Thanks!
