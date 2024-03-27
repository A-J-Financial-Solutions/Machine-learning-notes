# Algorithmic Trading Using A Combination Of Convolutional Neural Networks And LSTMs

Using the minute bar data, Jin Choi has experiemented with different types of models alongside their performances.

## Data Segmentation

| Segment    | Date Range          |
| ---------- | ------------------- |
| Training   | Jan 2021 - Jun 2022 |
| Validation | Jul 2022 - Jun 2023 |
| Evaluation | Jul 2023 - Dec 2023 |
| Test       | Jan 2024 - Mar 2024 |

## CNN

#### Evaluation Dataset 2H 2023

| Strategy           | Avg. Return | Std. Deviation |
| ------------------ | ----------- | -------------- |
| Best Model         | 0.00053%    | 0.05515%       |
| Avg. 5 Best Models | 0.00046%    | 0.07334%       |
| Buy and Hold       | 0.00014%    | 0.10535%       |

#### Test Dataset Jan 1, 2024 - Mar 4, 2024

| Strategy           | Avg. Return | Std. Deviation |
| ------------------ | ----------- | -------------- |
| Best Model         | -0.00018%   | 0.05128%       |
| Avg. 5 Best Models | 0.00030%    | 0.07480%       |
| Buy and Hold       | 0.00043%    | 0.11493%       |

## LSTM

#### Evaluation Dataset 2H 2023

| Strategy           | Avg. Return | Std. Deviation |
| ------------------ | ----------- | -------------- |
| Best Model         | 0.00091%    | 0.06844%       |
| Avg. 5 Best Models | 0.00077%    | 0.06795%       |
| Buy and Hold       | 0.00014%    | 0.10535%       |

#### Test Dataset Jan 1, 2024 - Mar 4, 2024

| Strategy           | Avg. Return | Std. Deviation |
| ------------------ | ----------- | -------------- |
| Best Model         | 0.00085%    | 0.06897%       |
| Avg. 5 Best Models | 0.00050%    | 0.07261%       |
| Buy and Hold       | 0.00043%    | 0.11493%       |

## CNN + LSTM

#### Evaluation Dataset 2H 2023

| Strategy           | Avg. Return | Std. Deviation |
| ------------------ | ----------- | -------------- |
| Best Model         | 0.00101%    | 0.07620%       |
| Avg. 5 Best Models | 0.00097%    | 0.07140%       |
| Buy and Hold       | 0.00014%    | 0.10535%       |

#### Test Dataset Jan 1, 2024 - Mar 4, 2024

| Strategy           | Avg. Return | Std. Deviation |
| ------------------ | ----------- | -------------- |
| Best Model         | 0.00081%    | 0.08329%       |
| Avg. 5 Best Models | 0.00047%    | 0.07760%       |
| Buy and Hold       | 0.00043%    | 0.11493%       |
