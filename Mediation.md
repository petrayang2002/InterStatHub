# Mediation Analyses


```mermaid
flowchart LR
    IV["Independent Variable"]-- c -->DV["Dependent Variable"];
```

```mermaid
flowchart LR
    IV["Independent Variable"]-- a -->MV["Mediator Variable"];
    MV["Mediator Variable"]-- b -->DV["Dependent Variable"];
    IV["Independent Variable"]-- c' -->DV["Dependent Variable"];
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

results = mediate(fit.mediator, fit.dv, treat='IV', mediator='MV', boot=T)
summary(results)
```


## STATA
