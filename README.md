# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

Add your answers to this markdown file.

## Solution

### Prob. 1
- It is just an approximation to real world results, we omit lots of factors to get a more refined model. When we calculate the time complexity we ignore constants and lower order terms than our max. For example, if our time complexity equation was $10*n^3+n^2$, we would say it behaves like O($n^3$), omitting the factor of 10 and $n^2$ so we have a simple model for extremely large values of $n$.
- Different machines can run different instructions for the same program, such as ARM vs x86. This can change the actual run-time with the same complexity
- Not all algorithms perform identically to their asymptotic analysis. This means that sometimes algorithm A can have a poor expectation with the analysis, but perform better than algorithm B in real life scenarios. For example, quick sort and heap sort have the same best case complexity but quick has a worse worst case complexity. So, if we had a worst-case scenario and we compared the two, we would be lead to believe that heap sort is the better algorithm, although quick sort almost always performs better on most machines.
  
### Prob. 2

A balanced tree is $O(\log(n))$, otherwise its $O(n)$. Assuming the worst case:

Let $C = \text{time constant,}$  $n=1000$, $t = 5$

$C*O(n)=t$

$C*1000=5$

$\therefore C=\frac{5}{1000}$

So, if $n=10000$:

$C*n=t$

$\frac{5}{1000}*10000=t$

$t = 50$

Therefore, it should take 50 seconds to find an element in 10,000 elements

### Prob. 3
- The machine could have hardware restrictions, such as exceeding the maximum amount of RAM space available.
- The first test (5 seconds) could have been executed on different architecture than your machine, causing different instructions to be executed.
- The new tree could exceed the amount of space available in the L1, L2, or L3 caches. This would cause the data to be moved to a higher, and thereby slower, space in the computer's memory. I.e., let's say L1 (very fast) can only hold 2,000 elements and L2 (fast) can hold 20,000. When the 1,000 element tree is loaded into memory, it will be loaded into L1, so it can access the data extremely fast. But, the larger 10,000 element tree would have to be loaded into L2, slowing down the process.

## Disclaimer

I used [https://stackoverflow.com/questions/2467751/quicksort-vs-heapsort](this) to make sure that I wasn't wrong in saying that quick sort performs better in general.

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
