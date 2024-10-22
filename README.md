# Multi-threaded-Sorting-algorithms-and-performance-evaluation
Multi-threaded Sorting algorithms and performance evaluation :
Insertion Sort, Merge Sort etc
This project is for demonstrating the Multi-threading feature for speeding up
execution. The coding is done using python programming. The timing information
is compared for different sizes of data sets with and without multi-threading for a
number of sorting algorithms. Python Multi-threading features are utilized.
Based on the output and the graph, here is a summary of which sorting algorithm performs better:

Observations from Timing Data:
1. Insertion Sort (Single-threaded):
   - Insertion Sort has poor scalability, especially as the dataset size increases. It took 497.8 secondsfor 100,000 elements, making it the slowest algorithm for large datasets.
   
2. Merge Sort (Single-threaded vs Multi-threaded):
   - Single-threaded Merge Sort performs very well across all dataset sizes. For 100,000 elements, it took **0.55 seconds**, whereas the Multi-threaded Merge Sort took 0.68 seconds. 
   - This shows that the multi-threading version of Merge Sort didn’t offer much speedup and was even slightly slower for small to medium dataset sizes. This is likely because Merge Sort already benefits from efficient divide-and-conquer recursion, and threading introduces overhead for smaller arrays.

3. Quick Sort (Single-threaded vs Multi-threaded):
   - Single-threaded Quick Sort is one of the fastest algorithms, completing the sorting of 100,000 elements in 0.16 seconds.
   - However, Multi-threaded Quick Sort took significantly longer, at 3.22 seconds. This may indicate that the overhead of threading outweighs the benefits for this particular algorithm and implementation.

4. Heap Sort (Single-threaded vs Multi-threaded):
   - Single-threaded Heap Sort performed well, taking 0.94 seconds for 100,000 elements.
   - Multi-threaded Heap Sort, however, took longer at 3.76 seconds, indicating that it doesn't benefit from multi-threading in this implementation, likely due to the complexity of managing the heap structure in parallel.

Hence,Conclusion
- Quick Sort  emerges as the fastest sorting algorithm for large datasets.
- Merge Sort (Single-threaded) is a strong performer and shows stable performance, but multi-threading doesn't seem to help it.
- Multi-threading overhead: Both Quick Sort and Heap Sort show significant slowdown with multi-threading due to thread management overhead, especially for large arrays. This might be because the threading model introduces complexity that diminishes the performance gains for these algorithms.
- Insertion Sort is not efficient for large datasets and was the slowest algorithm in the comparison.

From Graph we learnt that Insertion Sort grows exponentially in time as the dataset increases, and the other algorithms (Merge Sort, Quick Sort, and Heap Sort) show much better scalability, but the multi-threaded versions of Quick Sort and Heap Sort actually perform worse due to overhead.

So,Multi-threading doesn’t always improve performance and, in this case, actually degrades it for algorithms like Quick Sort and Heap Sort. The overhead involved in managing threads seems to outweigh the benefits.
