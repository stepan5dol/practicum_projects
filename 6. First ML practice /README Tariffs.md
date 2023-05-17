# Project Description

The mobile operator Megaline found out that many customers use archive tariffs. They want to build a system capable of analyzing customer behavior and offering users a new tariff: "Smart" or "Ultra".
You have at your disposal data on the behavior of customers who have already switched to these tariffs (from the course project "Statistical Data Analysis"). You need to build a model for the classification problem that will choose the appropriate tariff. You won't need data preprocessing — you've already done it.
Build a model with the maximum accuracy value. To pass the project successfully, you need to bring the proportion of correct answers to at least 0.75. Check accuracy on the test sample yourself.

## Data description

Each object in the dataset is information about the behavior of one user per month. Is known:

`calls` — number of calls,

`minutes` — total duration of calls in minutes,

`messages` — the number of SMS messages,

`mb_used` — consumed Internet traffic in MB,

`is_ultra` — what tariff was used during the month ("Ultra" — 1, "Smart" — 0).
