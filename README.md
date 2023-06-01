# Building solid data pipelines with PySpark

📚 A course brought to you by the [Data Minded Academy].

## Context

These are the exercises used in the course *Data Pipeline Part 2 at DSTI*.  
The course has been developed by instructors at Data Minded. The
exercises are meant to be completed in the lexicographical order determined by
name of their parent folders. That is, exercises inside the folder `b_foo`
should be completed before those in `c_bar`, but both should come after those
of `a_foo_bar`.

## Course objectives

- Introduce good data engineering practices.
- Illustrate modular and easily testable data transformation pipelines using
  PySpark.
- Illustrate PySpark concepts, like lazy evaluation, caching & partitioning.
  Not limited to these three though.

## Intended audience

- People working with (Py)Spark or soon to be working with it.
- Familiar with Python functions, variables and the container data types of
  `list`, `tuple`, `dict`, and `set`.

## Approach

Lecturer first sets the foundations right for Python development and
gradually builds up to PySpark data pipelines.

There is a high degree of participation expected from the students: they
will need to write code themselves and reason on topics, so that they can
better retain the knowledge.

Note: this course is not about writing the best pipelines possible. There are
many ways to skin a cat, in this course we show one (or sometimes a few), which
should be suitable for the level of the participants.

## Getting started

## Spark Set Up on Windows
Follow these instructions to set up JDK 11, Hadoop WinUtils, Spark binaries and environment 
variables on Windows/x64 System: [Click Here](https://app.tango.us/app/workflow/Setting-up-JDK--Hadoop-WinUtils--Spark-binaries-and-environment-variables-on-Windows-x64-System-ce23bd438117424c87009b2ac1fc82bd) 


## Run Spark Hello World

A spark program to test you have well set up Spark

### Prerequisites
Open a new terminal and make sure you're in the `spark-hello-world` directory. Then, run:

```bash
pip install -r requirements.txt
```

This will install any dependencies you might need to run this project in your virtual environment.

### Execute the main function
* Open the `main.py` file located under `spark-hello-world > src`.
* Go to the bottom of the file and locate `if __name__ == '__main__':`
* You will see a green arrow at the left, next to number 20
* Click on the green arrow to execute the main function
* Check the results in your terminal, you should see a couple of warnings in red (which you can ignore) and the result after those: `[1, 4, 9, 16]`


## Exercises

### Adding derived columns

Check out [dates.py](exercises/b_labellers/dates.py) and implement the pure
python function `is_belgian_holiday`. Verify your correct implementation by
running the test `test_pure_python_function` from
[test_labellers](tests/test_labellers.py). You could do this from the command
line with `pytest tests/test_labellers.py::test_pure_python_function`.

Return to [dates.py](exercises/b_labellers/dates.py) and
implement `label_weekend`. Again, run the related test from
[test_labellers.py](tests/test_labellers.py). It might be more useful to you if
you first read the test.

Finally, implement `label_holidays` from [dates](exercises/b_labellers/dates.py). 
As before, run the relevant test to verify a few easy cases (keep in mind that 
few tests are exhaustive: it's typically easier to prove something is wrong, 
than that something is right).

If you're making great speed, try to think of an alternative implementation 
to `label_holidays` and discuss pros and cons.

### Common business case 1: cleaning data

Using the information seen in class, prepare a sizeable dataset for 
storage in "the clean zone" of a data lake, by implementing the `clean` 
function of [clean_flights_starter.py](exercises/c_cleansers/clean_flights_starter.py).

### Peer review

Discuss the improvements one could make to 
[bingewatching.py](exercises/d_code_review/bingewatching.py).

### Common business case 2: report generation

Create a complete view of the flights data in which you combine the airline
carriers (a dimension table), the airport names (another dimension table) and
the flights tables (a facts table).

Your manager wants to know how many flights were operated by American Airlines
in 2011.

How many of those flights arrived with less than (or equal to) 10 minutes of
delay?

A data scientist is looking for correlations between the departure delays and
the dates. In particular, he/she thinks that on Fridays there are relatively
speaking more flights departing with a delay than on any other day of the week.
Verify his/her claim.

Out of the 5 categories of sources for delays, which one appeared most often in
2011? In other words, in which category should we invest more time to improve?
applications

[Data Minded Academy]: https://www.dataminded.academy/
