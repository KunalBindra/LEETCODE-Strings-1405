# LEETCODE-Strings-1405
### Example Input: 
Let’s consider the input: `a = 6`, `b = 3`, `c = 1`.

### Initial Setup:
- We initialize a priority queue (`pq`) with the counts and characters that are available (`a`, `b`, `c`).
- `pq` will hold the counts and their corresponding characters sorted by the highest count.

At the start:
- `pq = [(6, 'a'), (3, 'b'), (1, 'c')]`

### Dry Run Process:

1. **Iteration 1**:
   - Pop the top element from the priority queue: `(6, 'a')`
   - Add `'a'` to `result`: `result = "a"`
   - `a` count reduces to 5, so push `(5, 'a')` back into the queue.
   - `pq = [(5, 'a'), (3, 'b'), (1, 'c')]`

2. **Iteration 2**:
   - Pop the top element: `(5, 'a')`
   - Add `'a'` to `result`: `result = "aa"`
   - `a` count reduces to 4, so push `(4, 'a')` back into the queue.
   - `pq = [(4, 'a'), (3, 'b'), (1, 'c')]`

3. **Iteration 3**:
   - Pop the top element: `(4, 'a')`
   - We already have two consecutive `'a'`s in the result, so we look for another character.
   - Pop the next element: `(3, 'b')`
   - Add `'b'` to `result`: `result = "aab"`
   - `b` count reduces to 2, so push `(2, 'b')` back into the queue.
   - Push `(4, 'a')` back into the queue.
   - `pq = [(4, 'a'), (2, 'b'), (1, 'c')]`

4. **Iteration 4**:
   - Pop the top element: `(4, 'a')`
   - Add `'a'` to `result`: `result = "aaba"`
   - `a` count reduces to 3, so push `(3, 'a')` back into the queue.
   - `pq = [(3, 'a'), (2, 'b'), (1, 'c')]`

5. **Iteration 5**:
   - Pop the top element: `(3, 'a')`
   - Add `'a'` to `result`: `result = "aabaa"`
   - `a` count reduces to 2, so push `(2, 'a')` back into the queue.
   - `pq = [(2, 'a'), (2, 'b'), (1, 'c')]`

6. **Iteration 6**:
   - Pop the top element: `(2, 'a')`
   - We already have two consecutive `'a'`s, so we pick another character.
   - Pop the next element: `(2, 'b')`
   - Add `'b'` to `result`: `result = "aabaab"`
   - `b` count reduces to 1, so push `(1, 'b')` back into the queue.
   - Push `(2, 'a')` back into the queue.
   - `pq = [(2, 'a'), (1, 'b'), (1, 'c')]`

7. **Iteration 7**:
   - Pop the top element: `(2, 'a')`
   - Add `'a'` to `result`: `result = "aabaaba"`
   - `a` count reduces to 1, so push `(1, 'a')` back into the queue.
   - `pq = [(1, 'a'), (1, 'b'), (1, 'c')]`

8. **Iteration 8**:
   - Pop the top element: `(1, 'a')`
   - Add `'a'` to `result`: `result = "aabaabaa"`
   - `a` count reduces to 0, so we don’t push it back.
   - `pq = [(1, 'b'), (1, 'c')]`

9. **Iteration 9**:
   - Pop the top element: `(1, 'b')`
   - Add `'b'` to `result`: `result = "aabaabaab"`
   - `b` count reduces to 0, so we don’t push it back.
   - `pq = [(1, 'c')]`

10. **Iteration 10**:
    - Pop the top element: `(1, 'c')`
    - Add `'c'` to `result`: `result = "aabaabaabac"`
    - `c` count reduces to 0, so we don’t push it back.
    - `pq` is now empty, and we exit the loop.

### Final Result:
The longest diverse string is `"aabaabaabac"`.
