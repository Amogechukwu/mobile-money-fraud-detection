\# Stage 1: Business Problem



\## 1. Background (in plain English)

Mobile money lets people send, receive and withdraw money using a mobile

phone, without needing a traditional bank branch. It is widely used across

Africa and other emerging markets, and millions of transactions happen every

day.



Because so much money moves quickly and digitally, criminals try to take

advantage. \*\*Fraud\*\* here means a transaction made to steal money, for

example by taking over someone's account and moving their money out.



\## 2. The business problem

Imagine a mobile money company (a fintech). Fraud causes three problems:



| Problem | Why it matters |

|---|---|

| Direct money loss | Stolen money is often hard to recover |

| Loss of customer trust | Customers leave if they feel their money is unsafe |

| Regulatory pressure | Financial regulators expect companies to protect customers |



Checking every transaction by hand is impossible at this scale. The company

needs a way to \*\*spot suspicious transactions automatically\*\* and understand

\*\*where and how fraud happens\*\*, so it can prevent it.



\## 3. Who this project is for (stakeholders)

| Stakeholder | What they need |

|---|---|

| Fraud and risk team | To know which transactions to investigate first |

| Head of risk / management | A clear picture of how much fraud there is and what it costs |

| Product and operations team | Practical rules or controls that stop fraud without annoying genuine customers |



\## 4. Questions this project will answer

1\. How many transactions are fraudulent, and what share of the total is that?

2\. Which transaction types (for example transfers, cash-outs, payments) does fraud happen in?

3\. How do fraudulent transactions differ from normal ones (amounts, timing)?

4\. Does the company's existing rule (flagging very large transfers) catch fraud effectively?

5\. Can a model, trained on past transactions, predict which new transactions are likely to be fraud?



\## 5. Hypotheses (my starting assumptions, to be tested)

\- Fraud is concentrated in only one or two transaction types.

\- Fraudulent transactions are usually larger than normal ones.

\- A simple fixed rule misses a lot of fraud.



These come from reading about how the dataset was built. They may turn out to be wrong, and the analysis will confirm or reject each one.



\## 6. How success will be measured

There is a trade-off in fraud detection. The company must:

\- \*\*Catch as much real fraud as possible\*\* (called \*recall\*), and

\- \*\*Avoid wrongly blocking genuine customers\*\* (called \*precision\*).



Fraud is very rare, so a tool that says "no fraud" every time would look 99%

accurate but would be useless. Success is therefore not judged by overall

accuracy.



| Measure | Plain-English meaning | Target |

|---|---|---|

| Recall | Out of all real fraud, how much did we catch? | High (to be set after baseline results) |

| Precision | Out of everything we flagged, how much was really fraud? | Reasonable, so genuine customers are not blocked |

| Business view | Would the fraud team be able to use and trust the output? | Yes |



Exact targets will be set in the modelling stage, once a baseline is known.



\## 7. Scope

\*\*In scope:\*\* analysing the transactions, building dashboards, building a

prediction model, and a simple web app to demonstrate it.



\*\*Out of scope:\*\* connecting to a live payment system, handling real customer

data, and legal or regulatory decisions.



\## 8. Data source

PaySim: a synthetic (computer-simulated) mobile money dataset on Kaggle,

built from patterns in real transaction logs of a mobile money service in an

African country. About 6.3 million transactions.

Link: https://www.kaggle.com/datasets/ealaxi/paysim1



\## 9. Assumptions and limitations

\- The data is \*\*simulated\*\*, not real customer data. This is common in

&#x20; fraud research because real financial data is private. Findings show the

&#x20; method and approach, not the real fraud rate of any company.

\- Fraud in this dataset is rare (well under 1% of transactions), which makes

&#x20; detection harder. This will be confirmed in the next stage.

\- Some balance columns in the dataset reveal the answer once fraud has

&#x20; happened, so they cannot be used to predict fraud. This will be handled in

&#x20; the data stages.



\## 10. Planned approach

| Stage | What happens |

|---|---|

| 1. Business problem | This document |

| 2. Source and clean data | Download, check and clean the data, load into SQL |

| 3. Transform and visualise | SQL queries, Excel analysis, Power BI dashboard |

| 4. Analyse findings | Answer the questions above and make recommendations |

| 5. Train the model | Build and compare fraud prediction models |

| 6. Deploy the model | A web app where a transaction can be checked |

