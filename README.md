# ncalc
Repository for ncalc project

This python module provides classes that can be used to evaluate math expression contained in string. Most common class is Ncalc. It allows you evaluate expression contains variables ‘x’, ‘y’ and most common functions such as sin, cos, tg, log2, log10, exp, mod, exp and factorial. Furthermore you can build your own ‘calculator’ with your own operator precedences (don’t know why it can be needed), functions and variables. To build The Calculator see at Ncalc definition and do it like it:
  1. Define new class inherited from Matheval:

class Ncalc(Matheval):

  2. Using __init__ set up given math expression and context namely dictionary of variables and functions:
def __init__(self, mexp): super().__init__(mexp, { ‘x’: 1, ‘y’: 1, ‘factorial’: Ncalc.__factorial, })

  3. Wrap functions as ‘staticmethod’ or functions of module:
@staticmethod def __log10(a): return math.log10(a)

  4. That’s it. :)

Using:
'''python
>>> from ncalc.eval import Ncalc
>>> e = Ncalc(‘2*factorial(5)’)
>>> e.eval() 240
>>> e.expression = ‘1+mod(5, 2)+sin(0)’
>>> e.eval() 2.0
'''

P.S. This version can work wrong cause I didn’t test it as it’s necessary.
