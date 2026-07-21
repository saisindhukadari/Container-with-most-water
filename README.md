# Container With Most Water (Optimal Approach)

## Approach

This problem can be solved efficiently using the **Two Pointers** technique.

* Place one pointer at the beginning of the array (`left`).
* Place another pointer at the end of the array (`right`).
* At every step:

  * Calculate the width between the two pointers.
  * The container's height is determined by the shorter of the two lines.
  * Compute the current area.
  * Update the maximum area if the current area is larger.
* Move the pointer pointing to the **shorter line** toward the center.
* Continue until both pointers meet.

The intuition is that the shorter line limits the amount of water the container can hold. Moving the taller line cannot increase the area while the width decreases, so only the shorter line is moved.

## Algorithm

1. Initialize two pointers:

   * `left = 0`
   * `right = n - 1`
2. Initialize `maxArea = 0`.
3. While `left < right`:

   * Calculate the width.
   * Find the smaller of the two heights.
   * Calculate the current area.
   * Update the maximum area.
   * Move the pointer with the smaller height.
4. Return the maximum area.

## Time Complexity

* **O(n)**

Each pointer moves at most once across the array.

## Space Complexity

* **O(1)**

Only a constant amount of extra space is used.

## Key Insight

The width decreases whenever a pointer moves. Therefore, the only way to potentially obtain a larger area is by increasing the limiting (shorter) height. This is why the pointer at the shorter line is moved.

## Pattern

* **Technique:** Two Pointers
* **Difficulty:** Medium
* **Time Complexity:** O(n)
* **Space Complexity:** O(1)

## Interview Tip

Whenever you see a problem involving a **sorted structure**, **two ends**, or **choosing the best pair**, think about whether the **Two Pointers** technique can reduce a brute-force `O(n²)` solution to an `O(n)` solution.
