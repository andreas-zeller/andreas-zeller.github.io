# Fuzzing with Fandango – Task Sheet

## Your Task

Your task is to create a _Markdown_ fuzzer – that is, a tool that creates inputs for a Markdown processor such as [Pandoc](https://pandoc.org).
We start with simple Markdown syntax and end with a generator that creates full-fledged papers.
Use the [Fandango Fuzzer](https://fandango-fuzzer.github.io) for this task.


## Installing Fandango

1. Install Python.
2. From the command line, run `pip install fandango-fuzzer`.

## Installing Pandoc

We use [Pandoc](https://pandoc.org) as a Markdown converter.
Follow the [Installation Instructions](https://pandoc.org/installing.html).


## First Steps

Create a file `Markdown.fan` with these contents:

```python
<start> ::= "Some random text: " <random_text>
<random_text> ::= <printable>+
```

Use Fandango to fuzz inputs:

```
$ fandango fuzz -f Markdown.fan -n 10
```

Send the input to a Markdown processing tool such as [Pandoc](https://pandoc.org); redirect its output to a file that you can open in a browser.

```
$ fandango fuzz -f Markdown.fan -n 10 pandoc --to html > output.html
$ open output.html
```

Or create a LaTeX document from it:

```
$ fandango fuzz -f Markdown.fan -n 10 pandoc --to latex > output.tex
$ pdflatex output
```


## Task 1: Basic Markdown

Extend your Fandango spec `Markdown.fan` for Markdown that produces inputs with the following features:

* Random letters and digits
* Emphasis (`_Text_`, `*Text*`, `__Text__`, `**Text**`)
* Headers (`# Header`, `## Subheader`, ...)
* Links (`[Text](URL)`). Use a fixed URL for now.

Read the [Pandoc Manual](https://pandoc.org/MANUAL.html#pandocs-markdown) to understand which Markdown features are supported. To see the list of enabled extensions, use

```
$ pandoc --list-extensions=markdown
```

## Task 2: Fakers

Enhance your Fandango spec to make use of [_generators_](https://fandango-fuzzer.github.io/Generators.html). Use the [Python faker module](https://faker.readthedocs.io/en/master/) to produce

* URLs
* "Lorem Ipsum" Text blocks


## Task 3: Some Natural Text

Create a sub-grammar that creates _random English sentences_. Have rules and plenty of alternatives for subjects, verbs, objects, conjunctions, etc.
Combine this with the `faker` module to obtain names, places, ...


## Task 4: Tables

Enhance your Fandango spec to produce Markdown [tables](https://pandoc.org/MANUAL.html#tables). Create tables with a configurable, but fixed number of rows and columns; use `<row>{N}` to repeat a row N times.
Fill the tables with numbers.


## Task 5: Constraints

Use [constraints](https://fandango-fuzzer.github.io/Constraints.html) to ensure all numbers in tables are between 10 and 1000.


## Task 6: Cross-References

Create _references_ to headers. A Header `### My Awesome Section` can be referenced by taking the title, converting all letters to lowercase, and replacing all non-letters with spaces: `Read [my awesome section](my-awesome-section)`.

For this,

1. create a generator for headers that saves the reference in a table; 
2. create a second generator for references that takes a reference from the table.


## Task 7: Math

Because it's fun: Create a sub-grammar that produces LaTeX math formulas (`$...$`). Use `pandoc --to latex` to create output that you can run through LaTeX.

Be sure to create the most complex formulas ever seen.


## Task 8: Citations

Have your text include citations, rendered as footnotes:

```
Zamudio et al. introduced Fandango.[^1]

[^1]: Zamudio, Smytzek, Zeller: The Fandango Book, 2025
```

* As with references, you will need generators for this task.
* Use the `faker` module to produce author names.
* Use constraints to produce citation years (say, 1950-2025).


## Task 9: A Paper Generator

Put all the above together to create a _random scientific paper_ in Markdown (and then LaTeX, and then PDF). The best generated paper will get an award.


## Task 10: Large Language Models (Bonus)

For the abstract of the above paper, create a grammar that creates a random scientific-sounding title; then ask an LLM of your choice to create an abstract for it. Integrate the interaction into the `Markdown.fan` file.
