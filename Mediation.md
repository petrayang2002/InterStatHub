# Mediation Analyses

```mermaid
flowchart LR
    Independent Variable --> Mediator Variable;
    Mediator Variable --> Dependent Variable;
    Independent Variable --> Dependent Variable;
```


## SPSS



## R

```
fit.totaleffect <- lm(DV ~ IV, data = MyData) #for linear regression
fit.totaleffect <- glm(DV ~ IV, data = MyData, family = binomial()) # for logistic regression
summary(fit.totaleffect) 

fit.mediator=lm(MV ~ IV, data = MyData)
summary(fit.mediator)

fit.dv = lm(DV ~ MV + IV, data = MyData)
summary(fit.dv)

results = mediate(fit.mediator, fit.dv, treat='x', mediator='m', boot=T)
summary(results)
```


## STATA
