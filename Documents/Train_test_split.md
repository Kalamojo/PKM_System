# Train_test_split

---

## Original Data

| Sample | Condition | Timepoint | Validation |
| ------ | --------- | --------- | ---------- |
| S1     | AD        | 3m        | Test       |
| S2     | Healthy   | 3m        | Test       |
| S3     | AD        | 3m        | Train      |
| S4     | Healthy   | 3m        | Train      |
| S5     | AD        | 6m        | Test       |
| S6     | Healthy   | 6m        | Test       |
| S7     | AD        | 6m        | Train      |
| S8     | Healthy   | 6m        | Train      |
| S9     | AD        | 9m        | Test       |
| S10    | Healthy   | 9m        | Test       |
| S11    | AD        | 9m        | Train      |
| S12    | Healthy   | 9m        | Train      |

---

## Trains on:

| Sample | Condition | Timepoint | Validation |
| ------ | --------- | --------- | ---------- |
| S3     | AD        | 3m        | Train      |
| S4     | Healthy   | 3m        | Train      |
| S7     | AD        | 6m        | Train      |
| S8     | Healthy   | 6m        | Train      |
| S11    | AD        | 9m        | Train      |
| S12    | Healthy   | 9m        | Train      |

___

## Transfers Healthy to AD:

| Sample | Condition | Timepoint | Validation |
| ----------- | --------- | --------- | ---------- |
| S2          | Healthy   | 3m        | Test       |
| S6          | Healthy   | 6m        | Test       |
| S10         | Healthy   | 9m        | Test       |
