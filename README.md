# econ3916-lab13-multivariate-ols

# Lab 13: Multivariate OLS — What "Controlling For" Actually Does

## Objective

The purpose of this lab was to explore how including different control variables affects OLS regression estimates. I examined omitted variable bias, the Frisch-Waugh-Lovell theorem, collider bias, multicollinearity, and interaction terms. The main goal was to understand why adding more controls does not necessarily improve a regression model.

## Methods

I used Python, NumPy, pandas, and statsmodels to simulate datasets and estimate OLS regressions.

- **Omitted Variable Bias:** Compared regressions estimating the effect of education on wages with and without controlling for ability
- **Frisch-Waugh-Lovell Theorem:** Used residuals to demonstrate how controlling for ability isolates the relationship between education and wages
- **Collider Bias:** Examined how controlling for a variable affected by both the treatment and outcome can introduce bias
- **Multicollinearity:** Used variance inflation factors (VIF) to examine how highly correlated predictors affect standard errors
- **Interaction Terms:** Estimated how the return to experience differs between union and non-union workers
- **AI-Assisted Expansion:** Used AI to generate a function that compares regression specifications and checked its results against the original models

## Key Findings

### 1. Omitted Variable Bias

The short regression estimated a return to education of approximately $5,126, compared to the true effect of $2,500. After controlling for ability, the coefficient decreased to approximately $2,546.

This demonstrated how omitting a variable that affects both the explanatory variable and outcome can bias regression estimates.

### 2. Frisch-Waugh-Lovell Theorem

The FWL regression produced the same education coefficient as the multiple regression, approximately $2,546. This showed that controlling for ability is equivalent to removing the variation explained by ability from both education and wages before estimating their relationship.

### 3. Collider Bias and Multicollinearity

Controlling for a collider changed the treatment coefficient from approximately zero to −0.596, even though the true causal effect was zero. This demonstrated how including an inappropriate control can introduce bias.

The multicollinearity simulation showed that highly correlated predictors increased standard errors and made individual coefficients less precise.

### 4. Interaction Terms

The interaction model showed that the return to an additional year of experience differed by union membership.

- Non-union workers: Approximately $903 per additional year of experience
- Union workers: Approximately $504 per additional year of experience

The interaction coefficient was negative and statistically significant, indicating that non-union workers had a higher return to experience in the simulated data.

### 5. AI-Assisted Expansion

I used AI to create a function that runs multiple regression specifications and organizes their coefficients, standard errors, and sample sizes into a table.

Initially, one regression did not match because I had reused a variable name in an earlier exercise. After identifying and correcting the issue, all four regression specifications matched the original results.

This demonstrated the importance of checking AI-generated code rather than assuming its output is correct.

## Conclusion

This lab helped me understand that adding more controls does not always improve a regression. While controlling for confounders can reduce omitted variable bias, controlling for colliders can introduce bias, and controlling for mediators can remove part of the effect we want to estimate. I also learned that multicollinearity can make coefficients less precise without necessarily introducing bias.

Overall, the most important takeaway was that choosing appropriate controls requires understanding the relationships between variables, rather than simply including as many variables as possible.
