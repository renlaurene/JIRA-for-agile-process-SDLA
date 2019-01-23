# e_python
exercise by using python 
def dotProduct(listA, listB):
    total = 0
    for i in range(len(listA)):
        total += listA[i] * listB[i]
    return total
    

def deep_reverse(L):
    """ assumes L is a list of lists whose elements are ints
    Mutates L such that it reverses its elements and also 
    reverses the order of the int elements in every element of L. 
    It does not return anything.
    """    
    L.reverse()
    for subL in L:
        subL.reverse()
        

def dict_interdiff(d1, d2):
    dintersect = {}
    ddifference = {}
    for k in d1.keys():
        if k in d2.keys():
            dintersect[k] = f(d1[k], d2[k])
        else:
            ddifference[k] = d1[k]
    for k in d2.keys():
        if k not in d1.keys():
            ddifference[k] = d2[k]
    return (dintersect, ddifference)
    
    
def applyF_filterG(L, f, g):
    """
    Assumes L is a list of integers
    Assume functions f and g are defined for you. 
    f takes in an integer, applies a function, returns another integer 
    g takes in an integer, applies a Boolean function, 
        returns either True or False
    Mutates L such that, for each element i originally in L, L contains  
        i if g(f(i)) returns True, and no other elements
    Returns the largest element in the mutated L or -1 if the list is empty
    """
    to_remove = []
    for s in L:
        if not g(f(s)):
            to_remove.append(s)

    for s in to_remove:
        L.remove(s)
    return max(L) if L != [] else -1
    
    
def flatten(aList):
    result = []
    for i in aList:
        if type(i) == list:
            result.extend(flatten(i))
        else:
            result.append(i)
    return result
