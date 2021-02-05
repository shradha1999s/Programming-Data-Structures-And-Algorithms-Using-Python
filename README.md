# Programming-Data-Structures-And-Algorithms-Using-Python - WEEK 2


1. A positive integer m can be partitioned as primes if it can be written as p + q where p > 0, q > 0 and both p and q are prime numbers.
   Write a Python function primepartition(m) that takes an integer m as input and returns True if m can be partitioned as primes and False otherwise. 
   (If m is not positive, your function should return False.)

Solution : 

def primepartition(m):

    primelist=[]
    if m<0:
        return False
    else:
        for i in range(2,m + 1):
            for p in range(2,i):
                if (i % p) == 0:
                    break
            else:
                primelist.append(i)
                
        for x in primelist:
            y= m-x
            if y in primelist:
                return True
        return False
       
 
2. Write a function matched(s) that takes as input a string s and checks if the brackets "(" and ")" in s are matched: 
   that is, every "(" has a matching ")" after        it and every ")" has a matching "(" before it.
   Your function should ignore all other symbols that appear in s.   
   Your function should return True if s has matched brackets and False if it does not.
   
Solution : 
      
def matched(str):

    count = 0
    for i in str:
        if i == "(":
            count += 1
        elif i == ")":
            count -= 1
        if count < 0:
            return False
    return count == 0


3. A list rotation consists of taking the first element and moving it to the end. For instance, if we rotate the list [1,2,3,4,5], we get [2,3,4,5,1]. 
   If we rotate it again, we get [3,4,5,1,2].

   Write a Python function rotatelist(l,k) that takes a list l and a positive integer k and returns the list l after k rotations. 
   If k is not positive, your function should return l unchanged. Note that your function should not change l itself, and should return the rotated list.
      
Solution : 

  
def rotatelist(l,k):

    output_list = [] 
    k = k%len(l)
      
    for item in range(k, len(l)): 
        output_list.append(l[item]) 
   
    for item in range(0, k):  
        output_list.append(l[item]) 
          
    return output_list 
  
      
