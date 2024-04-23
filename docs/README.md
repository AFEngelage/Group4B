# EyeOn - Supermarket - Data Science case study

## Introduction

Brick-and-mortar grocery stores are always in a delicate dance with purchasing and sales forecasting. Predict a little over, and grocers are stuck with overstocked, perishable goods. Guess a little under, and popular items quickly sell out, leaving money on the table and customers fuming.

The problem becomes more complex as retailers add new locations with unique needs, new products, ever transitioning seasonal tastes, and unpredictable product marketing. Corporación Favorita Grocery Sales (CFGS), a large Ecuadorian-based grocery retailer, knows this all too well. They operate hundreds of supermarkets, with over 200,000 different product-store combinations.

CFGS has challenged you to help in the forecasting process. They currently rely on subjective forecasting methods with very little data to back them up and very little automation to execute plans. CFGS have collected a large dataset containing detailed point-of-sale data and data on external factors. They’re excited to see what insights you bring and what steps you suggest to improve their forecast.

## Case assignment

We invite you to shed some light on the CFGS case, with CRISP-DM as a guideline.

### Business understanding

Any good project starts with a deep understanding of the customer’s needs. The Business Understanding phase focuses on understanding the objectives and requirements of the project:

**Determine business objectives**: From a business perspective, what does CFGS really want to accomplish and then define business success criteria. For example, why is it important for CFGS to make their forecast less subjective?

**Assess situation**: Determine resources availability, project requirements, assess risks and contingencies, and conduct a cost-benefit analysis. How can the business context of the case be used in the analysis of the data?

**Determine data mining goals**: In addition to defining the business objectives, you should also define what success looks like from a technical data mining perspective. What insights can be gained from the sales data? What can we learn from item returns; can these be predicted?

**Produce project plan**: Select technologies and tools and define detailed plans for each project phase.

While many teams hurry through this phase, establishing a strong business understanding is like building the foundation of a house – absolutely essential.

### Data understanding

The data is provided in the `data` folder. Consider how this data can help you in solving this challenge:

**Collect initial data**: Acquire the necessary data and (if necessary) load it into your analysis tool. How complete is the data?

**Describe data**: Examine the data and document its surface properties like data format, number of records, or field identities.

**Verify data quality**: How clean/dirty is the data? Document any quality issues.

**Explore data**: Dig deeper into the data. Query it, visualize it, and identify relationships among the data. What kind of business dynamics do you recognize in the data? Which patterns do you see in the historical sales (trend, seasonality, events, week patterns, etc.)? What are your hypothesis on the underlying causes for the patterns that you find?

Based on your initial insights, what would be your advise to the sales manager on the period September to December. Use the data to support your advice and present your insights in a compelling story during the interview. We are keen to see not only your results, but also what approach you’ve taken. Use your creativity to find insights that will raise CFGS’s interest and shows them the value of their data.

### Data preparation 

This phase, which is often referred to as “data munging”, prepares the final data set(s) for modeling. It has five tasks:

**Select data**: Determine which data sets will be used and document reasons for inclusion/exclusion.

**Clean data**: Often this is the lengthiest task. Without it, you’ll likely fall victim to garbage-in, garbage-out. A common practice during this task is to correct, impute, or remove erroneous values.

**Construct data**: Derive new attributes that will be helpful. For example, convert the day, month, and year features to a single date feature.

**Integrate data**: Create new data sets by combining data from multiple sources.

**Format data**: Re-format data as necessary. For example, you might convert string values that store numbers to numeric values so that you can perform mathematical operations. Additionally, downcasting data can reduce the number of megabytes used by the data.

### Modeling

Here you’ll likely build and assess various models based on several different modeling techniques. This phase has four tasks:

**Select modeling techniques**: Determine which algorithms to try (e.g. regression, neural net).

**Generate test design**: Pending your modeling approach, you might need to split the data into training, test, and validation sets.

**Build model**: As glamorous as this might sound, this might just be executing a few lines of code like “reg = LinearRegression().fit(X, y)”.

**Assess model**: Generally, multiple models are competing against each other, and the data scientist needs to interpret the model results based on domain knowledge, the pre-defined success criteria, and the test design.

Although the CRISP-DM guide suggests to “iterate model building and assessment until you strongly believe that you have found the best model(s)”, in practice you should continue iterating until you find a “good enough” model, proceed through the CRISP-DM lifecycle, then further improve the model in future iterations. 

### Evaluation

Whereas the Assess Model task of the Modeling phase focuses on technical model assessment, the Evaluation phase looks more broadly at which model best meets the business and what to do next. This phase has three tasks:

**Evaluate results**: Do the models meet the business success criteria? Which one(s) should we approve for the business?

**Review process**: Review the work accomplished. Was anything overlooked? Were all steps properly executed? Summarize findings and correct anything if needed.

**Determine next steps**: Based on the previous three tasks, determine whether to proceed to deployment, iterate further, or initiate new projects.

### Deployment

“Depending on the requirements, the deployment phase can be as simple as generating a report or as complex as implementing a repeatable data mining process across the enterprise.” – [CRISP-DM Guide](https://www.the-modeling-agency.com/crisp-dm.pdf)

A model is not particularly useful unless the customer can access its results. The complexity of this phase varies widely. This final phase has four tasks:

**Plan deployment**: Develop and document a plan for deploying the model.

**Plan monitoring and maintenance**: Develop a thorough monitoring and maintenance plan to avoid issues during the operational phase (or post-project phase) of a model.

**Produce final report**: The project team documents a summary of the project which might include a final presentation of data mining results.

**Review project**: Conduct a project retrospective about what went well, what could have been better, and how to improve in the future.

## Using the data

Start with downloading or cloning this repository to your local machine. The data is provided in [Apache parquet](https://parquet.apache.org/) format, which requires [pyarrow](https://arrow.apache.org/docs/python/) (recommended) or [fastparquet](https://github.com/dask/fastparquet) (alternative):

```
pip install --user pyarrow
```

You can then load the data as follows

```python
import pandas as pd

df = pd.read_parquet('./data/history-per-year.parquet')
```

Note that `history-per-year.parquet` span multiple folders and files; it is [partitioned](https://arrow.apache.org/docs/python/parquet.html#reading-from-partitioned-datasets) by `year` and `month`. Do not change names of the folders or files.

## Attribution

This case study, including the data, was generously provided by [EyeOn](https://www.eyeon.nl/) for teaching purposes.
