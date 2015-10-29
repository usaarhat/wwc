# Data Carpentry with NLTK and IPython

This repository contains teaching materials for Saarland Uni's *Working With Corpora* program. It's been adapted from the repository for teaching materials and additional resources used by Research Platforms Services to teach *Python*, *IPython* and the *Natural Language Toolkit* (*NLTK*).

All the materials used in the workshops are in this repository. In fact, cloning this repository will be our first activity together as a group. To do that, just open your terminal and type/paste:

```shell
git clone https://github.com/interrogator/wwc.git
```

Though we'll be working with blank notebooks in our training sessions, everthing we cover lives as a complete notebook in the `resources/completed-notebooks` directory. These notebooks are useful for remembering or extending what you learned in during training. Alternatively, they may be useful for those who cannot attend our sessions face-to-face.

Below is a basic overview of the four-session lesson plan. You can click the headings to view complete versions of the IPython Notebooks we'll be using in each sessions. The materials are always evolving, and pull requests are always welcome.

## [Session 1: Orientation](http://nbviewer.ipython.org/github/resbaz/nltk/blob/master/resources/completed-notebooks/session-1.ipynb)

In this session, you will learn how to use IPython Notebooks, as well as how to complete basic tasks with Python/NLTK. 

* Getting up and running
* What exactly are *Python*, *IPython* and *NLTK*?
* Introductions to *IPython Notebook*
* Overview of basic Python concepts: *significant whitespace*, *input/output types*, *commands and arguments*, etc.
* Introduction to NLTK
* Quickstart: *US Inaugural Addresses Corpus*
* Plot key terms in the inaugural addresses longitudinally
* Discussion: *Why might we want to use NLTK? What are its limitations?*

In this session, we also devote more time to the fundamentals of Python, learning how to create and manipulate different kinds of data. In the first half of the session, we discuss:

* Working with variables
* Writing functions
* Creating frequency distributions

## [Session Two: Corpus linguistic tasks](http://nbviewer.ipython.org/github/resbaz/nltk/blob/master/resources/completed-notebooks/session-2.ipynb)
In the second half of the session, we put our existing skills to work in order to investigate the corpora that come bundled with NLTK. The major kinds of analysis we cover are:

* Sentence splitting
* Tokenisation
* Keywords
* n-grams
* Collocates
* Concordancing

## [Session 3: The Fraser Corpus](http://nbviewer.ipython.org/github/resbaz/nltk/blob/master/resources/completed-notebooks/session-3.ipynb)

Details forthcoming

## [Session 4: Getting the most out of what we've learned](http://nbviewer.ipython.org/github/resbaz/nltk/blob/master/resources/completed-notebooks/session-4.ipynb)

Details forthcoming

## Adding to this repository

You're more than welcome to submit a pull request with changes to our course materials.

The `.ipynb` files used by both students and instructors are generated using plain `.py` files with IPython's `nbconvert` utility. Accordingly, the best way to modify our course materials is to update the `.py` file, rather than the `.ipynb` file. These live in `resources/notebook-source-files`.



Longer functions may be archived in `resources/scripts.py`, so that they may be imported by instructors/helpers on students' notebooks if need be.
