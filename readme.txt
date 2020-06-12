CONTENT
This is kinda cool, maybe?
Yeah, I guess.
Rude. This is amazing.
You're right. I'm sorry.
It's alright. I love you.
Love you, too.

Okay, last night I was having trouble sleeping, so I tried to figure out how to
sort a list of numbers larger than the size of a computer's memory. I couldn't
figure out how to do the whole thing in my head, so I decided I would revisit
it later when I could look and visually see the patterns.

//say we have the numbers 1-12 randomly arranged and we needed to put them in
order. But, our computer only has memory large enough to store three numbers at
a time.

//start by parsing through the whole list (a), sorting as many sub-lists as you
//can. Then write the result to a new output (b).
[[7 12 6]a1  [5 3 8]a2  [4 2 9]a3  [1 10 11]a4] a
  «    »      «   »      «   »      «     »
[[6 7 12]b1  [3 5 8]b2  [2 4 9]b3  [1 10 11]b4] b

//now, consider each of the sub-lists as a stack. Pop a number off as many
//sub-lists as you can until memory is full, which in this case is three numbers
//find the lowest one and write it to output c. Repeat for all three numbers.
«              »
b1:     b2:    b3:    b4:
12      8      9      11
7       5      4      10
6*      3*     2*     1

[] c

//repeat until no more items are on any of the work-in-progress stacks
«              »
b1:     b2:    b3:    b4:
12                    11
7       8             10
6*      5*     9*     1

[2 3 4] c

//repeat
«              »
b1:     b2:    b3:    b4:
                      11
                      10
12*      8*    9*     1

[2 3 4 5 6 7] c

//okay, now we're done with that step. Take output c and treat it as a sub-list.
«              »
b1:     b2:    b3:    b4:
                      11
                      10
                      1

[2 3 4 5 6 7 8 9 12] c

//then repeat the same process, comparing c to a4 and storing the result in d
«              »
c:      b4:
12
9
8
7
6
5
4       11
3       10
2*      1*

[]d

//repeat

«              »
c:      b4:
12
9
8
7
6
5
4       11
3*      10*

[1 2]d

//repeat

«              »
c:      b4:
12
9
8
7
6       11
5*      10*

[1 2 3 4]d

//repeat

«              »
c:      b4:
12
9
8       11
7*      10*

[1 2 3 4 5 6]d

//repeat

«              »
c:      b4:
12      11
9*      10*

[1 2 3 4 5 6 7 8]d

//repeat

«              »
c:      b4:
12      11
9*      10*

[1 2 3 4 5 6 7 8 9 10]d

//repeat

«              »
c:      b4:
12*     11*

[1 2 3 4 5 6 7 8 9 10]d

//repeat

«              »
c:      b4:

[1 2 3 4 5 6 7 8 9 10 11 12]d

//okay! we ran out of numbers to sort. That means we must be done! The final
//result we wrote to must be our properly sorted list, and we only looked at a
//max of 3 numbers at a time in memory!
