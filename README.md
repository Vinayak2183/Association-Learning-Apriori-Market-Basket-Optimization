# Association Rule Learning with Apriori Algorithm

This repository contains an implementation of the Apriori algorithm for association rule learning, applied to market basket analysis. The goal is to discover interesting relationships between products purchased together, which can be useful for recommendation systems, store layout optimization, and promotional strategies.

## Overview

The Apriori algorithm is a classic method for mining frequent itemsets and generating association rules. It works by identifying items that frequently co-occur in transactions and then deriving rules based on their support, confidence, and lift metrics.

### Key Concepts:
- **Support**: The frequency of an itemset in the dataset.
- **Confidence**: The likelihood of item Y being purchased given that item X is purchased.
- **Lift**: The ratio of observed support to expected support if X and Y were independent. A lift greater than 1 indicates a meaningful association.

## Dataset

The dataset used in this project is `Market_Basket_Optimisation.csv`, which contains transaction data from a retail store. Each row represents a transaction, and each column contains a product purchased in that transaction.

## Implementation Steps

1. **Data Preparation**:
   - The dataset is loaded into a Pandas DataFrame.
   - Transactions are converted into a list format required by the Apriori algorithm.

2. **Model Training**:
   - The Apriori algorithm is applied to the transaction data with the following parameters:
     - `min_support=0.003`: Itemsets must appear in at least 0.3% of transactions.
     - `min_confidence=0.2`: Rules must have at least 20% confidence.
     - `min_lift=3`: Rules must have a lift value of at least 3.
     - `min_length=2` and `max_length=2`: Only rules with exactly 2 items are considered.

3. **Results Extraction**:
   - The generated rules are organized into a Pandas DataFrame for clarity.
   - Results are sorted by descending lift to highlight the strongest associations.

## Results

The top association rules, sorted by lift, are displayed in a DataFrame. For example:
- `fromage blanc` and `honey` have a high lift of 5.16, indicating a strong association.
- `light cream` and `chicken` also show a significant relationship with a lift of 4.84.

## How to Use

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
