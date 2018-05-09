# Interactive Notebooks for Sharing and Collaboration

By Oscar Vargas Torres

## About

Interactive notebooks are an excellent tool to learn and share your knowledge. In this talk I'll introduce several of these to allow you to start helping others to learn and practice what you can teach others.

## How this talk will help me to become a better consultant (developer/software engineer)

+ Teaching others on a subject you know helps you to become more interested in the people you work with. It gives you the opportunity to practice what you know and improve your abilities to explain concepts to others.
+ Interactive Notebooks are a very practical way to share knowledge, mixing text and code that you can actually execute in your own computer.

## How to use talk material

The material of this talk consist of two notebooks. To be able to fully experiment (interactively) with these, you would need to install the following Jupyter kernels in your development environment

1. REQUIRED: a Python3 kernel (basic usage)
2. OPTIONAL: a SageMath kernel (this is for more advanced usage)
3. OPTIONAL: other kernels (Haskell, Scala, JavaScript, Java, etc. according to your interests). This would require effort from your side, because you will need to install less known kernels.

__NOTE:__ The author used Jupyterlab to write the material.

I recommend the Python3.X version, although you may find the 2.X version more suitable for your daily needs.

* [Installing the Anaconda Python Distribution for your OS](docs/installing-anaconda-for-your-os.md)
* [Installing Jupyterlab](docs/installing-jupyterlab.md)

### Algebra1-Python-Puro.ipynb

You only need a Python3 (Jupyter) kernel to use (interactively) this notes.

Please make sure you have installed the following python packages to be able to execute the code cells:

+ `matplotlib`
+ `numpy`
+ `scipy`
+ `sympy`

#### Notes:

+ Double click in the *markdown* cells, as well as in the *code* cells, to be able to modify and explore it's contents.
+ Pay special attention in the way you can typeset math content using LaTeX and MathJax for a beautiful document including math.
+ `scipy` is used to do a curve interpolation using Chebysev polynomials. This is only for illustration purposes of what kind of (advanced) numerical computations can be done with Python.
+ The contents of the notes explore (very briefly) the usage of Simbolic Math using `sympy`.

### Algebra1.ipynb

You would need to have a SageMath kernel installed in your development environment to be able to interact with these notes.

We started our sessions with some Math notation and concepts, revolving around Set Theory. And this notes are useful to practice the concepts with an advanced Open Source Computer Algebra System (CAS): [Sage](http://www.sagemath.org/). Do not hesitate to contact me if you are interested in advanced mathematics using a CAS.