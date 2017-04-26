# amazon-interview
Interview question:

Given a list of points on the XY plane, return the k points closest to the origin. (I was asked later in the interview to remove any duplicates from the list.)

My solution was originally written in Java.
1) Use a hashset to remove duplicates. If a point has been visited, skip it. If not, add it to the hashset and results list.
2) Sort the results list by distnace to origin, ascending.
3) return sublist [0 - k].
4) Runs in O(n log n)

I recently found another way to do this using a priority queue that runs slightly faster.
1) Use a hashset to remove duplicates, same as above.
2) Create a Priority Queue, descending order, elements keyed to their distance from the origin.
3) for each Point p in given points:
    if p is smaller than largest point in the queue:
      dequeue top point.
      enqueue current item.
4) dequeue all points into new list.
5) results list will be in descending order so reverse it.
6) return results.
7) Runs in O(n log k).

Comparison using <code>Process.GetCurrentProcess().TotalProcessorTime</code> where n = 100 million random points whose values range from [-100, 100) and k = 2500:

<code>

</code>
