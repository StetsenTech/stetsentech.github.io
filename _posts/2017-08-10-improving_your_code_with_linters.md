---
layout: post
title:  "Improving Your Code with Linters"
date:   2017-08-07 11:30:34 -0400
categories: python marshmallow linter code
---
# Improving Your Code with Linters

## Introduction to Linters

### What is a linter

A linter is a program that is designed to analyze source code based on a set of configurations in order to maintain the quality of code being produced by programmers.

A linter can check for errors, inspect code design style based on a given guideline, warn against unsafe practices, find unused variables, and much more.

### What a Linter is Not

While a linter can ensure that code is being developed in a healthy manner, a linter does not provide insight on logic being programmed.  Logic is dependent on the developers working on the code. A linter should be used as an aid to guide the development of code.

## Why use a Linter

### Unify Coding Style Differences

In the world of programming, solutions can be approached in varies different ways. Code that looks drastically different may produce the same result. There are disputes on what are the best practices for each programming language, but what are some of the root causes such differences? The differences in the code could be a result of a programmer not knowing how to style properly, use of different standard style guide, or personal preference to ignore or mix standards.  Regardless of the reason, this makes code difficulty to read.

### Identify Common Coding Errors

While a programmer is coding, they aren't always aware when a problem falls through the cracks whether it be programatic or logical. A linter can pick up on some of the simple ones such as a clause in conditional never being met or a variable potentially never being assigned a value.
