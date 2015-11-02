# Data Carpentry with NLTK and IPython

This repository contains teaching materials for Saarland Uni's *Working With Corpora* program. It's been adapted from the repository for teaching materials and additional resources used by [*Research Platforms Services*](http://melbourne.resbaz.edu.au/) at the University of Melbourne to teach *Python*, *IPython*, *Jupyter* and the *Natural Language Toolkit* (*NLTK*).

Essentially, the idea of both programs is to run free training in reproducible research methods and tools via [a cloud platform](https://dit4c.github.io/), so that nobody has to worry about installation/operating system/specs problems. All code is written and executed within [Jupyter Notebooks](http://jupyter.org/), allowing easy access to earlier input and output, as well as the rich display of text/images.

All the materials used in the workshops are in this repository. In fact, cloning this repository will be our first activity together as a group. To do that, just open your terminal and type/paste:

```shell
git clone https://github.com/interrogator/wwc.git
```

Though we'll be working with blank notebooks in our training sessions, everthing we cover lives as a complete notebook in the `resources/completed-notebooks` directory. These notebooks are useful for remembering or extending what you learned in during training. Alternatively, they may be useful for those who cannot attend our sessions face-to-face.

Below is a basic overview of the four-session lesson plan. You can click the headings to view complete versions of the IPython Notebooks we'll be using in each sessions. The materials are always evolving, and pull requests are always welcome.

## [Session 1: Orientation](https://github.com/interrogator/wwc/blob/master/resources/completed-notebooks/nltk-session-1-complete.md)

In this session, you will learn how to use the Jupyter Notebook, as well as how to complete basic tasks with Python/NLTK. 

* Getting up and running
* What exactly are *Python*, *Jupyter* and *NLTK*?
* Introductions to *Jupyter*
* Overview of basic Python concepts: *significant whitespace*, *input/output types*, *commands and arguments*, etc.
* Introduction to NLTK
* Quickstart: *US Inaugural Addresses Corpus*
* Plot key terms in the inaugural addresses longitudinally
* Discussion: *Why might we want to use NLTK? What are its limitations?*

In this session, we also devote more time to the fundamentals of Python, learning how to create and manipulate different kinds of data. In the first half of the session, we discuss:

* Working with variables
* Writing functions
* Creating frequency distributions

## [Session Two: Corpus linguistic tasks](https://github.com/interrogator/wwc/blob/master/resources/completed-notebooks/nltk-session-2-complete.md)

In this session, we put our existing skills to work in order to investigate the corpora that come bundled with NLTK. The major kinds of analysis we cover are:

* Sentence splitting
* Tokenisation
* Keywords
* n-grams
* Collocates
* Concordancing

We finish off the session by writing a regular-expression based concordancer.

## [Session 3: Working with corpora](https://github.com/interrogator/wwc/blob/master/resources/completed-notebooks/nltk-session-3-complete.md)

Now that we need know the basics of Python and corpus linguistics, we need to figure out how to get our own data into forms that we can interrogate.

> More details forthcoming!

## [Session 4: Getting the most out of what we've learned](https://github.com/interrogator/wwc/blob/master/resources/completed-notebooks/nltk-session-4-complete.md)

Our final session involves:

* Answering important issues raised by students in earlier sessions
* Discussing local workflows:
  * How do we get everything set up on own own devices?
  * How do we get help when things go wrong?
  * How should I store/share my code?
* Brainstorming ideas for the future

## Adding to this repository

You're more than welcome to submit a pull request with changes to our course materials.

The `.ipynb` files used by both students and instructors are automaticallygenerated using [notedown](https://github.com/aaren/notedown). Accordingly, the best way to modify our course materials is to update the `.md` file, rather than the `.ipynb` file. These also live in `resources/completed-notebooks`.

Longer functions/solutions to challenges may be archived in `resources/scripts.py`, so that they may be imported by instructors/helpers on students' notebooks if need be.
