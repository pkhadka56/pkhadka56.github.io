---
title: "Why I Prefer SLOs Over Uptime Targets"
date: 2026-11-10
description: "Uptime percentages hide what users actually feel. SLOs make reliability a shared, measurable decision."
tags: ["sre", "reliability"]
---

# Understanding SLOs and Error Budgets

"We need 99.99% uptime" sounds like a clear goal, but what does it actually mean for users?

A service can be up while users are experiencing failed requests or slow responses. Uptime alone doesn't tell us whether the service is working as expected.

## What is an SLO?

An SLO (Service Level Objective) defines how reliable a service should be. It consists of three parts:

- **SLI:** What we measure, such as successful requests or response times.
- **SLO:** The reliability target, such as 99.9% successful requests over 30 days.
- **Error Budget:** The amount of failure we can tolerate while meeting that target. For a 99.9% SLO, that's 0.1%.

## Why Error Budgets Matter

Error budgets help teams balance feature development and reliability.

When the budget is healthy, teams can continue shipping features. When it's burning quickly, it's a signal to pay more attention to reliability.

Once the budget is exhausted, the team should prioritize fixing reliability issues over releasing new features. Developers and SREs investigate what went wrong and work on improvements before normal feature releases resume.

This policy should be agreed upon in advance, so everyone knows what to expect.

## Getting Started

1. Pick one user-facing feature or service.
2. Define an SLI you can measure.
3. Set a realistic SLO.
4. Calculate the error budget.
5. Monitor error-budget consumption using burn-rate alerts.

Start small. One meaningful SLO is better than ten dashboards nobody looks at.