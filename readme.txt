PyTsetlinMachineCUDA - Massively Parallel and Asynchronous Architecture for Logic-based AI
Using logical clauses to represent patterns, Tsetlin machines (https://arxiv.org/abs/1804.01508) have obtained competitive performance in terms of accuracy, memory footprint, energy, and learning speed on several benchmarks (image classification, regression and natural language understanding). In the parallel and asynchronous architecture implemented here, each clause runs in its own thread for massive parallelism. The clauses access the training examples simultaneously, updating themselves and local voting tallies in parallel. A team of Tsetlin Automata composes each clause. The Tsetlin Automata thus drive the entire learning process. These are rewarded/penalized according to three local rules that optimize global behaviour.
There is no synchronization among the clause threads, apart from atomic adds to the local voting tallies. Hence, the speed up!

This document is a how-to for running the experiments detailed in the paper.
All data required is found in data/, all experiment code is found in experiments/.

================
Requirements
================
Python 3.7.x, https://www.python.org/
Numpy, http://www.numpy.org/
PyCUDA, https://documen.tician.de/pycuda/
Scikit-learn, https://scikit-learn.org/
NLTK, https://www.nltk.org/
_______________________________________________________________

================
Installation
================

python setup.py build && python setup.py install
_______________________________________________________________

================
Experiments

================
Novelty Detection
================
Score calculation using TM:

$python noveltyscore.py ../data/BBC

Then, classification using MLP on above generated scores:

$python classification_novelty.py ../data/BBC


or
$python noveltyscore.py ../data/20_newsgroups
$python classification_novelty.py ../data/20_newsgroups

---------------------------------------------------------
---------------------------------------------------------