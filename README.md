[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=12257451&assignment_repo_type=AssignmentRepo)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

## Analysis 

For the leftmost selection, the probability of obtaining a good pivot is $\frac{1}{2}$, while there is a $\frac{1}{4}$ chance for both a bad pivot on the low end and a bad pivot on the high end. 

Considering the median-of-three strategy, with pivots $(L, M, R)$  where “ $L$ ” represents a pivot that is too small, “ $R$ ” represents a pivot that is too large, and “ $M$ ” represents a good pivot.

$(L) = \frac{1}{4}$ (probability of a pivot too small)

$(R) = \frac{1}{4}$ (probability of a pivot too large)

$(M) = \frac{1}{2}$ (probability of a good pivot)



Exploring all possible combinations $(LLL, LLR, LRR, RRR, LLM, LMR, MRR, LMM, MMR, MMM)$ and calculate their probabilities. 


The calculation of each combination:- 

$LLL => \frac{1}{4} * \frac{1}{4} * \frac{1}{4} = \frac{1}{64}$

$LLR => \frac{1}{4}  * \frac{1}{4} * \frac{1}{4} = \frac{1}{64}$ 

$LRR => \frac{1}{4} * \frac{1}{4} * \frac{1}{4} = \frac{1}{64}$

$RRR => \frac{1}{4} * \frac{1}{4} * \frac{1}{4} = \frac{1}{64}$

$LLM => \frac{1}{4} * \frac{1}{4} * \frac{1}{2} = \frac{1}{32} * \frac{2}{2} = \frac{2}{64}$ 

$LMR => \frac{1}{4} * \frac{1}{2} * \frac{1}{4}  = \frac{1}{32} * \frac{2}{2} = \frac{2}{64}$ 

$MRR => \frac{1}{2} * \frac{1}{4} * \frac{1}{4} = \frac{1}{32} * \frac{2}{2} = \frac{2}{64}$

$LMM => \frac{1}{4} * \frac{1}{2} * \frac{1}{2} = \frac{1}{16}  * \frac{4}{4} = \frac{4}{64}$

$MMR => \frac{1}{2} * \frac{1}{2} * \frac{1}{4} = \frac{1}{16} * \frac{4}{4} = \frac{4}{64}$

$MMM => \frac{1}{2} * \frac{1}{2} * \frac{1}{2} = \frac{1}{8} * \frac{8}{8} = \frac{8}{64}$ 



-> Possibilities of the combinations:

$LLL$ has 1 possibility $=> \frac{1}{64}* 1 = \frac{1}{64}$ 

$LLR$ has 3 possibilities -> $RLL, LLR, LRL => \frac{1}{64} * 3 = \frac{3}{64}$ 

$LRR$ has 3 possibilities -> $LRR, RLR, RRL => \frac{1}{64} * 3 = \frac{3}{64}$

$RRR$ has 1 possibilities $=> \frac{1}{64} * 1 = \frac{1}{64}$

$LLM$ has 3 possibilities -> $LLM, LML, MLL => \frac{2}{64} * 3 = \frac{6}{64}$

$LMR$ has 6 possibilities -> $LMR, MLR, MRL, RML, RLM, LRM => \frac{2}{64} * 6 = \frac{12}{64}$

$MRR$ has 3 possibilities -> $MRR, RRM, RMR => \frac{2}{64} * 3 = \frac{6}{64}$

$LMM$ has 3 possibilities -> $LMM, MLM, MML => \frac{4}{64} * 3 = \frac{12}{64}$

$MMR$ has 3 possibilities -> $MMR, RMM, MRM => \frac{4}{64} * 3 = \frac{12}{64}$

$MMM$ has 1 possibilities $=> \frac{8}{64} * 1 = \frac{8}{64}$  



Now we add all the probabilities of the combinations that result in a good pivot for the median-of-three strategy
$LMR + LMM + MMR + MMM$

$\frac{12}{64} + \frac{12}{64} + \frac{12}{64}  + \frac{8}{64} = \frac{44}{64} $

$\frac{44}{64}$ gets simplified to $\frac{11}{16}$ , which is approximately 68.75 % . 

Overall, the median-of-three method demonstrates a higher probability of 68.75 % for selecting a good pivot compared to the leftmost element selection 50 %.


-> Sources Used: Referred to countermooshroom analysis
