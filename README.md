[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Bi-S25fM)
# Reverse Insertion Sort

Consider the code for insertion sort we covered in class:

```javascript
function insertionSort(arr) {
  for(var i = 1; i < arr.length; i++) {
    var val = arr[i];
    var j;
    for(j = i; j > 0 && arr[j-1] > val; j--) {
      arr[j] = arr[j-1];
    }
    arr[j] = val;
  }
  return arr;
}
```

Change this function such that it works from the end of the array rather than
the beginning, `insertionSortReverse()` -- only the direction of
iterating over the elements is reversed, the array is still sorted the same way
(ascending). Add your code in `code.js`. Test your new function; I've provided
some basic testing code that uses [jsverify](https://jsverify.github.io/) in
`code.test.js`.

## Average-Case Time Complexity of Insertion Sort

In the lectures, we covered that insertion sort has best-case time complexity of
$\Theta(n)$ and worst-case time complexity of $\Theta(n^2)$. What is the
average-case time complexity ($\Theta$)?

Hint: Think about what happens in each iteration of the loop, and how often the
loop is executed. Keep in mind that for asymptotic analysis we don't care about
constant factors.

Describe your reasoning and the conclusion you've come to. Your reasoning is
most important -- you can easily find the answer, but you need to demonstrate
that you've understood the concept. Add your answer to this markdown file.

For insertion sort, the best case is $\Theta(n)$ because it will iterate through every element in the list, so n times.
In the average case it will go through the inner loop because it needs sorted. 1/2 of the elements will need swapped because it isn't in descending order, and it isn't already sorted.
For each swap the inner loop has to compare it to all the already sorted elements and for the last element that could mean n-1 comparisons and swaps. 
So if around 1/2 of the array needs sorted, and the outer loop iterates n times, and the inner loop could iterate i-1 times for any element,
then it would be 1/2 * (n-1). Multiply this by the iterations of the outer loop n and we have (n^2 -n)/2. Discarding of the constant factors we get n^2.
So the average case for insertion sort is $\Theta(n^2)$.
