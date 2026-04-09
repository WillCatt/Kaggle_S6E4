# Kaggle Playground Series S6E4

This project explores the Season 6 Episode 4 Kaggle Playground competition, where the goal is to predict irrigation need across three classes: `Low`, `Medium`, and `High`. The dataset is synthetically generated, so the analysis is intended to stay general and objective rather than lean too heavily on real-world agricultural assumptions.

## Competition framing

The competition is evaluated with balanced accuracy. That metric matters here because the target is imbalanced, with `High` irrigation need appearing much less often than `Low` or `Medium`. Balanced accuracy averages recall across classes, which makes it a better fit than plain accuracy for judging whether the model is learning all three outcomes instead of defaulting toward the majority class.

## EDA approach

The main exploratory notebook uses dual-axis predictor plots to compare feature distributions against average irrigation need. This makes it easier to quickly identify variables that appear to separate the target well and which features may only carry weaker standalone signal. The notebook focuses on broad, repeatable patterns rather than overfitting interpretation to a synthetic generator.

## Initial observations

- The target is clearly imbalanced, so class-aware evaluation is necessary from the start.
- `Soil_Moisture`, `Temperature_C`, `Humidity`, and `Previous_Irrigation_mm` appear to be the strongest individual predictors.
- Several categorical variables show weaker standalone separation, which suggests interactions may matter more than raw category averages.
- Because the data is synthetic, strong relationships may reflect generator logic more than realistic agronomic behavior.

## Current direction

The immediate goal is to build a reliable multiclass baseline, validate it with stratified cross-validation, and then improve performance through feature interactions and model comparison. The work begins in notebooks and will move into reusable code as the modeling pipeline stabilizes.
