---
title: CI Pipeline tuning
keywords: CI pipeline
sidebar: cip_sidebar
permalink: ci_tuning.html
summary: "Steps to take if your connector isn't valid."
folder: ci-pipeline
---

The CI Pipeline emails you a CSV file with detailed results on the test cases defined in your connector's configuration file. We provide a Tableau Workbook that gives you a high-level overview of how many tests passed in each category, as well as the tools to drill down to individual test cases. This allows you to see the expected values versus actual values, the generated SQL statement, and any errors Tableau or your product reported while running or attempting the test.

For a test that failed, the *Error msg* column provides information on the failure. The generated log files included in your email can provide additional detail, as well as looking through logs on your product’s side.

For more information, see [Fixing TDVT Test Failures](tdvt-test-case.html).
