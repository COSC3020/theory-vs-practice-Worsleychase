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
- Asymptotic analysis assumes typically assumes worst-case or average-case data sets. Obviously not all data is worst-case or average-case. Depending on what you are analyzing (worst or average or best), you can get wildly different results than expected.
  
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
- There could be more constants in the binary search algorithm that are not accounted for at such a relatively small n. The generalized $C$ constant does not take into account all overhead. For example, there could be a constant $D$, that only happens when the list is opened so it only happens once. For larger lists that take more overall time it would have little effect, but for smaller lists that don't take long to iterate through the opening delay $D$ would seem extremely large. 

## Disclaimer

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
