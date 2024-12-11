java c
CSE 240 Homework 08, Fall 2024   (50 points)
Due Saturday, December 7th, 2024 at   11:59PM, plus one   day   grace period
Introduction
The aim of   this assignment is to make sure that you understand   and   are   familiar with the   concepts   covered in the lectures on Prolog.    By the end of   the   assignment, you   should have
•             strong concept of   logic /   declarative paradigm;
•             strong concept of   facts, rules,   and   questions   in   Prolog.
•             Compared and contrasted the programming C++,   Scheme,   and Prolog.
•             Prolog list operations   and manipulations
•             Prolog recursive rules with multiple nested calls
Reading: Text Chapter 5 and lecture slides. Also read Text Appendix B.4 Prolog TutorialYou   are   expected   to   do   most   of   the   assignment   outside   the   class   meetings.   Should   you   need   assistance, or have questions about the   assignment, please   contact   the   instructor   or   the   TA during   their office hours.
You are encouraged to ask and   answer   questions   on the   course   discussion   board   and   in   the   course   Discord server.    (However, do not share your   answers   in   the   course   discussion board.)
Practice Exercises (no submission required)
1.                Answer   the    multiple-choice   questions   in   text   section   5.9   that   have   been   covered   in   the   lectures.
2.                Complete the questions 2 through   5 in   text   section   5.9.
3.                Lookup   the   Unix   command   table   in   Appendix   B.1 and   read   the   Prolog   tutorial   in   B.4.
4.                Log onto general.asu.edu and execute the Unix   commands   and   Prolog   exercises.
5.                Follow the Prolog tutorial in Text   Appendix B.4 or the tutorials given in the course Web site,   start   GNU   Prolog   and   try   following   simple programs   (build-in   functions).   Don't   forget   the   period at the end   of   the   statement.


|    ?- write(hello)   .                                                    % hello   is   a   constant   */
|    ?- write(Hello)   .                                              %   Hello   is   avariable.   Its   address   will   be   displayed*/
|    ?- write('helloworld')   .                % a   string   is   printed   */
| ?- read(Y), write('The   variable   entered   is   '),   write(Y), nl. /* nl   prints   a   newline.   Type   a   period   and   an   enter   at the   end   of   the   input   */   |      ?- X   is   2+2.
|      ?- Y   is   5*8.
|      ?- Y   is   2**10.
|    ?- length([a,b, x, y,   2,   45, z],   L).
|    ?- append([a,b,   c,   d],   [4,   6,   8],   LL).
|    ?- append(X,Y,[a,b,c]). Then, type   ";" to   obtain   all   possible   answers.   
|    ?-             X   is   [1   |   [2   |   [3   |   []]]], write(X). Explain   the   output.
6.                Use trace and notrace before and after your   questions   in   Question   5.   For   example
|   ?- trace.
|   ?-                X   is   [1   |   [2   |   [3   |   []]]], write(X). Explain   the   output.
|   ?- notrace.
Programming Assignment (50 points)
1.          Consider   the   following   diagram   of   a   familytree:
   
Implement the family relationships in a Prolog factbase:
Note: The section in the highlighted box above has been completed for you.



/* Factbase for a family tree. It consists of facts and rules. *//* Facts */male(abe). male(rob).male(jim).female(joy).female(ana).father_of(abe, ana). /* abe is the father of ana */father_of(abe, rob). /* abe is the father of rob */father_of(abe, jim). /* abe is the father of jim */mother_of(joy, rob). /* joy is the mother of rob */mother_of(joy, jim). /* joy is the mother of jim */mother_of(joy, ana). /* joy is the mother of ana *//* Complete the facts given in the diagram above *//* Rules */





Open the given file 1FamilyTreeSolution.pl using a text editor such as pico or vim on a Unix   operating system. You may write the program on your own computer using any editor such as   notepad and upload the program to the general server to compile and execute.
Compile the program using the command:
$ gplc 1FamilyTreeSolution.pl
This should create an executable that you can then run using the following command:
$ ./1FamilyTreeSolution
This will enter you into the GNU Prolog programming environment where your program has   already been executed.
Ask questions by typing, e.g.:
|?- father_of(mark, beth).
|?- mother_of(beth, tom).
To exit from GNU Prolog, type the end-of-file character at the main Prolog prompt ^d (Ctrl-d).
|?- ^d
You can find a complete set of GNU Prolog commands at:
http://www.gprolog.org/manual/gprolog.html



For all the following questions, please label the question number in a comment. For example,   if Question 2.1 asks you to define a   rule   named   is_male   (X)   that   returns   "yes"   (or   "true")   if   X is the father of a member of   the family, then your code   should   look   like:
/* Question   1.1   */
is_male(X)   :-
male(X);
father_of(X, _).
This is a reading check. If   you see this, congratulations. You may use this   in your   solution.   Now, you can start to add your   code   into the program.Complete   the   program   by   adding   facts   for   the   remaining   members   on   the   familytree.   The   section inside of   the highlighted box has already been completed for you for clarification. Please pay close   attention   when   adding   the   remaining   family   members.   spelling   counts   and   all   letters   should   be   lowercase.
1.1 Define   (add   into代 写CSE 240 Homework 08, Fall 2024C/C++
代做程序编程语言   the   factbase)   a   rule   called   is_male(X)   that   returns   “yes”   (or   “true”)   if   X   is a   male   or   the   father   of   a   member   of   the   family.
Note:   the   system   will   return   a   "yes",   if it   finds   a   "true"   answer   and   there   exist   no   more   true   answers. The system   will   return "true ?"   if   it finds a "true" answer and   there are still   possibly   further matches. In this case, if   you press enter, it will return "yes" and   stop. If   you type   "   ;",   it will continue to search   for further   answers.
1.2                   Define   (add   into   the   factbase) a   rule   called   is_female(X)   that   returns   "yes" (or   "true")   if X   is   a   female   or   the   mother   of   a   member   of   the   family.
1.3    Define      a      rule      called      grandmother_of(X,    Z) that      returns      “yes”    (or      “true”)    if   X   is      a   	grandmother   of Z. Define   another   rule   called   grandfather_of(X, Z)   that   returns   “yes” (or “true”) if   X   is   a   grandfather   of   Z. (you   can   use   1.5   parent_of(X, Y)   rule)
1.4             Define   a   rule   called   sibling_of(X, Y)   that   returns   “yes” (or   “true”) if   X   is   a   sibling   of   Y.   Note: a   family   member   cannot   be   their   own   sibling.   (you   can   use   1.5   parent_of(X, Y)
rule)
1.5          Define   a   rule   called   parent_of(X, Y)   that   returns   “yes” (or   “true”) if   X   is   aparent   of   Y.
1.6 Define   a   rule   called   descendent_of(X, Y)   that   returns   “yes” (or   “true”) if   X   is   a   descendent of Y. A descendant,   in   the   context   of a   family   tree,   refers   to   any   individual   directly   related   through   a   series   of   parent-child   relationships,   e.g.   if   joy   is   the   parent   of   jim,   and   jim   is   the   parent   of   kim, then   kim   is   considered   a   descendant   of   both   joy   and   jim. Note: you   will   need to   use   recursion   as   well   as   the   parent_of   rule.    (you   can   use   1.5   parent_of(X, Y)   rule)


2.          Consider   the   following   factbase   for   the   games   planetDrop   and   mechaTech.   [12 points]
planetDrop
mechaTech
genre: action
genre: rpg
focus:
focus:
gameplay
story
-            mechanics
-            characters
-            framerate
-            plot
graphics
world
-            rendering
-            design
-            meshes
-            culture
In 2GamesSolution.pl, complete the following:
Create facts for the genres: genre(X, Y)   where X   is   a   game   and Y   is   a   genre.
Create facts for the focuses:   focus(X, Y)   where X   is a game   and   Y   is   a   focus.
Create   facts   for   the   elements:   element(X, Y)   where   X   is   a   focus   and   Y   is   an   element.
2.1          Create   a   rule   game(X, Y)   where   X   is   a   game   and   Y   are   the   genre   and   the   focuses   of that   game.   For   example,   game(planetDrop,   X) should   return   (use      ;   to   browse through the results):
X   =   action   ?   ;
X =   gameplay   ?   ;
X = graphics
2.2          Create a rule creation(X, Y)   where X   is a   game and Y   are the elements of   that game.   For   example,   creation(planetDrop, X)   should   return:
X = mechanics   ?   ;
X =   framerate   ?   ;
X   =   rendering   ?   ;
X = meshes




3.          In 3QuicksortSolution.pl, you will re-implement the Quicksort given in textbook and lecture   slides.   In the   given   example, the   first   (left-most)   element   of   the   given   list   is   selected   as the   pivot. In this question, you must choose the second element of   the list as the pivot. Hint:   You   can represent the input list into pairs:   [First|[Pivot|Tail]].   You must write comments to   indicate   the   size-n   problem,   stopping   condition   and   its   return   value,   size   m-problems,   and   construction   of   the   size-n   problem   from   size-m   problems.
Test   case:
| ?- qsort2([8,   3,   4,   12,   25,   4,   6,   1,   9,   22,   6],   Sorted).
It returns:
Sorted   =   [1,3,4,4,6,6,8,9,12,22,25]
4.          A premium pizza is comprised of   exactly 40 ounces   of   toppings.   The   available   toppings   are listed   below   with   their   corresponding   weight   (in   ounces).   There   can   be   multiple   entries   of   each topping, as long as the total weight is   equal   to   40   ounces.
Topping
Weight (ounces)
Pepperoni
Sausage
Bacon
Onion
Mushroom
4
10
6
5
7
For   example, a   pizza   can   contain   1 topping   ofpepperoni, 2 toppings   ofsausage,   1   topping   of bacon, and 2 toppings   of   onion   :   1*4   + 2*10   + 1*6   + 2*5   = 40   (ounces)
A   pizza cannot   contain   7 toppings of   bacon   :    7   *   6   = 42 > 40
A   pizza   cannot   contain   only   3 toppings   ofsausage   : 3*10   = 30   < 40
In   4PizzaSolution.pl, define   a   rule   pizza(P, S, B, O, M)   to   find   out   how   many   of   each   topping can   be   contained   on   a   pizza,   where   arguments   P,   S,   B,   O,   and   M   represent   the   weights   (in   ounces) of   the Pepperoni,   Sausage, Bacon, Onion, and Mushroom toppings, respectively.
Your pizza rule will be used to find the outputs to questions similar to below:   Test   Case:
| ?-   pizza(1,   S,   1,   O,   M).
It   returns: (use      ;   to   browse   through   the   results)

M = 0 M = 0 M = 0 M = 0 O = 6O = 4 O = 2 O = 0 S = 0                        S= 1 S = 2 S = 3





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
