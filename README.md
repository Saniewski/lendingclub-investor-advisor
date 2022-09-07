# LendingClub Payback Advisor
A project aiming to help LendingClub's investors predict whether the borrower will pay back their loan. By utilizing decision trees and random forests, we can help investors make the right decision when evaluating a candidate for their loan.

## Description
The `decision-tree-random-forest.ipynb` notebook contains:
* visualization of the data,
* data preprocessing,
* decision tree model training, making predictions,
* random forest model training, making predictions,
* evaluation of both models' performance
* final insights.

## The Data
The dataset consists of the following features:
* `credit.policy`: 1 if the customer meets the credit underwriting criteria of LendingClub.com, and 0 otherwise.
* `purpose`: The purpose of the loan (takes values "credit_card", "debt_consolidation", "educational", "major_purchase", "small_business", and "all_other").
* `int.rate`: The interest rate of the loan, as a proportion (a rate of 11% would be stored as 0.11). Borrowers judged by LendingClub.com to be more risky are assigned higher interest rates.
* `installment`: The monthly installments owed by the borrower if the loan is funded.
* `log.annual.inc`: The natural log of the self-reported annual income of the borrower.
* `dti`: The debt-to-income ratio of the borrower (amount of debt divided by annual income).
* `fico`: The FICO credit score of the borrower.
* `days.with.cr.line`: The number of days the borrower has had a credit line.
* `revol.bal`: The borrower's revolving balance (amount unpaid at the end of the credit card billing cycle).
* `revol.util`: The borrower's revolving line utilization rate (the amount of the credit line used relative to total credit available).
* `inq.last.6mths`: The borrower's number of inquiries by creditors in the last 6 months.
* `delinq.2yrs`: The number of times the borrower had been 30+ days past due on a payment in the past 2 years.
* `pub.rec`: The borrower's number of derogatory public records (bankruptcy filings, tax liens, or judgments).
* `not.fully.paid`: 1 if the borrower has not fully paid back their loan for any reason, and 0 otherwise.

## Project Outcome & Conlusion
Out of all 2874 borrowers, the random forest model predicts that only 14 borrowers will not fully pay back their loan, while in reality 463 borrowers didn't pay back their loan. These are definitely not good predictions. On the other hand, the single decision tree predicted that 518 borrowers will not fully pay back their loan, while in reality 463 borrowers didn't pay back their loan. These are much better predictions.

The single decision tree is a better choice in this case, because LendingClub.com wants to be sure that the borrower will pay back their loan. The random forest model is not a good choice, because it is too optimistic and it will lead to a lot of bad loans.

We can draw two conclusions:
1. Knowing the domain is crucial. In this case, we know that LendingClub.com wants to be sure that the borrower will pay back their loan, so we should keep that in mind when evaluating the models and choose accordingly.
2. The accuracy of the model is not the only thing that matters. We should also consider other values in the confusion matrix and analyze the model's performance in more detail.
