# Statistics for AI

This repository contains a collection of mathematical statistics and probability derivations relevant to artificial intelligence, machine learning, and data science.

The goal of this repo is to build clear, readable derivations of important statistical ideas, with an emphasis on intuition, step-by-step reasoning, applications to AI, and the deeper patterns behind each problem.

Rather than treating each derivation as an isolated result, I try to identify the general idea that the problem teaches. For example, in the German Tank Problem, the key pattern is that we can estimate an unknown total from a small sample by using the largest observed value and adding an estimated missing gap above it. In the Coupon Collector Problem, the key pattern is that total waiting time can be broken into smaller geometric waiting times. These patterns are useful because they appear repeatedly in statistics, machine learning, and AI systems.

The notes are also written to be both human-readable and machine-retrievable. Alongside acting as study notes, they are intended to serve as retrieval context for a Retrieval-Augmented Generation system that can answer questions about statistics and machine learning theory.

## Contents
| No. | Topic | Description |
|---|---|---|
| 01 | [Mean and Variance MLE](derivations/01-mean-and-variance-MLE.md) | Derivation of the maximum likelihood estimators for the mean and variance of a normal distribution. |
| 02 | [Weighted Mean](derivations/02-weighted-mean.md) | Derivation of the inverse-variance weighted mean estimator. |
| 03 | [Poisson Distribution MLE](derivations/03-poisson-distribution-MLE-different-sized-intervals.md) | MLE derivation for a Poisson process with different-sized observation intervals. |
| 04 | [Buffon's Needle](derivations/04-buffons-needle.md) | Geometric probability derivation and connection to Monte Carlo estimation. |
| 05 | [German Tank Problem](derivations/05-german-tank-problem.md) | Estimating an unknown population maximum from observed serial numbers. |
| 06 | [Coupon Collector Problem](derivations/06-coupon-collector-problem.md) | Expected waiting time to collect all coupon types, with AI dataset coverage applications. |
| 07 | [Secretary Problem](derivations/07-the-secretary-problem.md) | Optimal stopping problem and exploration-exploitation interpretation. |
| 08 | [Lighthouse Problem](derivations/08-lighthouse-problem.md) | Bayesian estimation problem involving a Cauchy likelihood. |

## Focus on reusable patterns

Each derivation is written with the aim of extracting a reusable mathematical pattern.

For example:

- **German Tank Problem:** estimate an unknown maximum from observed samples by correcting the largest observation with an estimated missing gap.
- **Coupon Collector Problem:** split a complex waiting-time problem into simpler geometric waiting times.
- **Secretary Problem:** balance exploration and exploitation by sampling first, then committing once a strong candidate appears.
- **Weighted Mean:** combine noisy measurements by giving more weight to observations with lower error variance.
- **Poisson MLE:** estimate an event rate by dividing total observed events by total observed exposure time.
- **Buffon's Needle:** introduces Monte Carlo simulation by showing how repeated random experiments can be used to estimate a mathematical quantity, in this case $\pi$.
- **Lighthouse Problem:** shows how to derive the density of an unknown variable by rewriting it in terms of a variable with a known distribution, then applying continuous random variable transformation. It also introduces the Cauchy distribution as a likelihood model.

This makes the notes useful not only as derivations, but also as a collection of statistical reasoning patterns that can be applied to AI and machine learning problems.

## Connection to my RAG system

These derivation notes are also designed to be used as retrieval context for a Retrieval-Augmented Generation system.

Each derivation is written in markdown so that it can be parsed, chunked, embedded, stored in a vector database, and retrieved when a user asks a related statistics or machine learning question.

For example, if a user asks:

> Why is the German Tank MLE biased?

the RAG system should be able to retrieve the German Tank derivation and use the relevant section on estimator bias to generate a grounded explanation.

This gives the repository two purposes:

- a human-readable collection of probability and statistics notes
- a structured knowledge base for an AI question-answering system

## Why this repository exists

Many machine learning methods rely on ideas from probability, statistics, and optimisation. This repository is my attempt to deeply understand these foundations by deriving results from first principles.

Rather than only recording final formulas, each file aims to explain:

- what problem is being solved
- what assumptions are being made
- how the likelihood or probability model is constructed
- how the estimator or result is derived
- why the result makes intuitive sense
- where the idea appears in AI or machine learning

## Repository structure

```text
assets/
  buffons-needle-images/
  coupon-collector-images/
  german-tank-problem-images/
  lighthouse-problem-images/
  mean-and-variance-MLE-images/

derivations/
  01-mean-and-variance-MLE.md
  02-weighted-mean.md
  03-poisson-distribution-MLE-different-sized-intervals.md
  04-buffons-needle.md
  05-german-tank-problem.md
  06-coupon-collector-problem.md
  07-the-secretary-problem.md
  08-lighthouse-problem.md
```

## Current focus

The current focus is on classical probability and statistics problems that are useful for building intuition in machine learning, including:

- maximum likelihood estimation
- biased and unbiased estimators
- Bayesian reasoning
- geometric probability
- waiting-time problems
- optimal stopping
- sampling and coverage problems
