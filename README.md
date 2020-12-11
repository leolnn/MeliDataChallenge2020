# MeliDataChallenge2020

## Winner model for Mercado Libre Data Challenge 2020

This solution is called Efecto Bolo! and in honour of this lovely name, it was the first place of the [final leaderboard](https://ml-challenge.mercadolibre.com/final_results)!

## The challenge

>  "Build a Machine Learning model to predict next purchase based on the user’s navigation history."
>
> https://ml-challenge.mercadolibre.com/


## Data
The dataset provided for this competition contains users' navigation histories (list of visited items and searches before the purchase), and the purchased item (target).

The training set contains 413.163 rows, and the test set used for submissions has 177.070 rows.

Additionally, there is a dataset with the catalog of all available items for making predictions with the catalog of all available items for making predictions (2M items). It contains some extra information about the products, such as the price, the listing's title, and categories.

> https://ml-challenge.mercadolibre.com/downloads

## Evaluation

Submissions were evaluated using the average NDCG score of the top ten predicted items. This metric takes into account the order of the set of recommendations, assigns a relevance score if we hit the target purchase, and also a lower score for those predicted items with the same domains (it's like a category) of the target. The latter means that the solution could focus on item domains. There are 7,894 domains in the catalog, so this is an easier task than item predictions.

> https://ml-challenge.mercadolibre.com/rule

## Models

The strategy used for this challenge has several parts:

### Implicit rating

### Matrix Factorization

## Results

| Model                                 | Local score       | Public score  | Private score  |
|---------------------------------------|-------------------|---------------|----------------|
| Baseline (sorted visited items)       | 0.2085            |               |                |
| Simple Implicit rating                | 0.2639            |               |                |
| Items to items                        | 0.2889            | 0.28755       |                |
| ALS Ensamble (Last Submission)        | 0.3180            | 0.31293       | 0.30920        |

> https://ml-challenge.mercadolibre.com/final_results
