# Rossmann Store Sales Prediction
## Introduction
An end-to-end Machine Learning (ML) project to predict the sales of a store given a set of inputs, including the promotions, competition, school and state holidays, seasonality, and locality.

This project is originally a case study for the application process at one of the leading mobile wallet and payment companies in the Philippines. Unfortunately, the author was not able to submit the task on time. However, the author used the resources provided as an opportunity to learn, in particular, how to write deployment codes for building a reproducible and scalable ML pipelines.

## Background
Rossmann is Germany's second-largest drug store chain. You are provided with historical sales data for 1,115 Rossmann stores. 

### Goal
The task is to forecast the "Sales" column. Note that some stores in the dataset were temporarily closed for refurbishment.

### Deliverables
1. Train a model on the Rossmann dataset to predict sales
2. Build a REST API that predicts the sales given a set of input
3. Containerized deployment - the REST API should be inside a container
4. CI/CD - use CI/CD when building an image of the container and when deploying the image to the server

## Data
The files provided are:
1. train.csv - historical data including Sales
2. store.csv - supplemental information about the stores

### Data fields
- **Id** - an Id that represents a (Store, Date) duple within the test set
- **Store** - a unique Id for each store
- **Sales** - the turnover for any given day (this is what you are predicting)
- **Customers** - the number of customers on a given day
- **Open** - an indicator for whether the store was open: 0 = closed, 1 = open
- **StateHoliday** - indicates a state holiday. Normally all stores, with few exceptions, are
closed on state holidays. Note that all schools are closed on public holidays and
weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None
- **SchoolHoliday** - indicates if the (Store, Date) was affected by the closure of public
schools
- **StoreType** - differentiates between 4 different store models: a, b, c, d
- **Assortment** - describes an assortment level: a = basic, b = extra, c = extended
- **CompetitionDistance** - distance in meters to the nearest competitor store
- **CompetitionOpenSince[Month/Year]** - gives the approximate year and month of the
time the nearest competitor was opened
- **Promo** - indicates whether a store is running a promo on that day
- **Promo2** - Promo2 is a continuing and consecutive promotion for some stores: 0 = store
is not participating, 1 = store is participating
- **Promo2Since[Year/Week]** - describes the year and calendar week when the store
started participating in Promo2
- **PromoInterval** - describes the consecutive intervals Promo2 is started, naming the
months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts
in February, May, August, November of any given year for that store
