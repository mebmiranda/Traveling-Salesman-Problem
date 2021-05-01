# Traveling-Salesman-Problem
## Objective 
Generate 50 random locations with x and y coordinates ranging from 0 to 1000 and random initial path. Compute the initial total distance which is the distance from the initial starting point to the 2nd location, up to the last location, and from the last location going back to the initial location. Perform Simulated Annealing to find a better path.

## Method
   - Generate 50 random locations with x and y coordinates ranging from 0 to 1000
   - Generate random initial path
   - Compute the distance for each path (from one location to another)
   - Compute the distance of the whole path (from first point up to last point and going back to the first point)
   - Perform Simulated Annealing
   - Determine the new path and compute the path's total distance

## Analysis
   - Euclidean distance formula can be used to compute the distance from one location to another
       - dist(A,B) = sqrt((B[0] - A[0])\*\*2 - (B\[1\] \-\ A\[1\])\*\*2)
   - Generate 2 random numbers to determine which cities will be swap on the next iteration
   - Randomly swap two cities in the path
   - If this new path is shorter, accept it. Otherwise accept it with probability p
   - p = exp((old distance - new distance)/k) where k is the temperature of the system
   - If the new solution is strictly better, meaning new distance < old distance, then accept the new path
   - If the new solution is equal or worse, compute p and generate random probability. If p is better than the generated random probability, accept new path.
   - The new path's total distance is better compared to the initial path's total distance. However, we are not guaranteed that the path is the optimal path

## Conclusion
The initial path's total distance is 15683.14. The Simulated Annealing Path total distance is 1941.29 which is significantly better compared to the initial path.

**Note:** There might be other better path combinations available. Simulated Annealing does not always provide an optimal solution.
