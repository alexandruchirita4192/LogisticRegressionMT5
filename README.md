# MT5 LogisticRegression ONNX Package

This package contains:
- train_mt5_logistic_regression_classifier.py
- MT5_LogisticRegression_ONNX_Strategy.mq5
- README.md

## Model
Multiclass LogisticRegression:
- SELL = -1
- FLAT = 0
- BUY = 1

## Features
13 scale-invariant features:
- ret_1
- ret_3
- ret_5
- ret_10
- vol_10
- vol_20
- vol_ratio_10_20
- dist_sma_10
- dist_sma_20
- zscore_20
- atr_pct_14
- range_pct_1
- body_pct_1

## Python requirements
pip install numpy pandas scikit-learn skl2onnx onnx MetaTrader5

## Training example
python train_mt5_logistic_regression_classifier.py --symbol XAGUSD --timeframe M15 --bars 20000 --horizon-bars 8 --train-ratio 0.70 --output-dir output_lr_XAGUSD_M15_h8

## Notes
LogisticRegression often produces softer probabilities than boosting or MLP.
A good first MT5 search zone is:
- InpEntryProbThreshold: 0.10 -> 0.40
- InpMinProbGap: 0.00 -> 0.10
