# Cython development

"[Cython](https://github.com/cython/cython) is a language that makes writing C extensions for Python as easy as Python itself." 

Currently, the framework has one cython module in `cython_pathfinding`. 
It implements same interface its python counterpart `python_pathfinding` but is about x25 faster. 

To make getting started with the framework as easily as possible, no compiled moduled should be *required* to use botbowl because it requires a C/C++ compiler.
So either develop cython modules with python counterparts or use [Cython's pure mode](https://cython.readthedocs.io/en/latest/src/tutorial/pure.html). 
The only reason for not using Cython's pure mode is if you what to build part of the module in C/C++.  

Here's the suggested workflow for developing cython modules without pure mode: 
 1. Write tests. 
 2. Write python code that passes the tests.
 3. Setup the cython module, remember to add it to [setup.py](setup.py)
 4. Extened the test suite to include the cython module, see [tests/ai/test_pathfinding.py](tests/ai/test_pathfinding.py) for example.
 5. Implement the cython module. 

This means, if you want to work on the pathfinding module (e.g. add Break Tackle to the list of skills considered) 
you would have to implement it in python and cython. You would have to do step (1), (2), and (5) of the steps above.  

If you want to make a certain part of the framework faster (e.g. the Game class) you would do steps (3), (4) and (5). 

Feel free to ask questions and discuss in the discord channel!