
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