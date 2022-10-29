- ## 📝Definition
	- Algorithm is a procedure which maps each input to a **single** output (**deterministic**). Algorithm **solves** a problem if it returns a correct output for every problem input.
- ## ⛈Characteristics / Properties
  There are 2 properties to say about algorithm.
	- ### Correctness
		- For **small** inputs, can use case analysis to prove.
		- For arbitrarily **large** inputs, algorithm must be **recursive** or **loop**. Normally we use **induction** to prove the correctness
	- ### Efficiency
		- Once the algorithm is proved correct, it has to be measured in efficiency.
		- Following are a few rules to measure the efficiency of an algorithm
			- **machine independent** -> meaning we don't evaluate with machines because a same algorithm may have different performance on different computer!
			- **Quantify OPS** -> meaning counting number of fixed-time operations algorithm takes to return
			- **inputs⬆  time⬆** -> meaning the size of input directly affect the time of computation
			- $n$ -> usually the amount of input is denoted as $n$
			- **polynomial​** $n^c$ -> meaning the algorithm is efficient enough if it returns in polynomial computation time with respect to amount of input
			- **None** -> meaning sometimes an efficient algorithm does not exist.
		- #### The Efficiency Table
		  id:: 6326888e-2beb-4ec0-bca1-0ba863acc203
			- | input | constant    | logarithmic      | linear      | log-linear        | quadratic      | polynomial    | exponential                 |
			  | ----- | ----------- | ---------------- | ----------- | ----------------- | -------------- | ------------- | --------------------------- |
			  | $n$   | $\Theta(1)$ | $\Theta(\log n)$ | $\Theta(n)$ | $\Theta(n\log n)$ | $\Theta (n^2)$ | $\Theta(n^c)$ | $2^{\Theta(n^c)}$           |
			  | 1000  | 1           | $\approx$10      | 1000        | $\approx$10,000   | 1,000,000      | 1000$^c$      | 2$^{1000}\approx$10$^{301}$ |
			  | Time  | 1 $ns$      | 10 $ns$          | 1 $\mu s$   | 10$\mu s$         | 1$ms$          | 10$^{3c-9}$s  | 10$^{281}$ millenia         |
		- #### The Efficiency Chart
			- ![name](../assets/Comparison_computational_complexity.svg){:height 300, :width 300}
- ## 🗃Example  
  Example is the most straightforward way to understand a mathematical concept.
	- 📌A descriptive example of algorithm
	  id:: 631a1ab2-80b1-4c96-851e-295efa3cbfde
		- Target
			- An algorithm to see whether there are students with same birthday in a same classroom.
		- Algorithm
			- A. Maintain a record of names and birthdays(initially empty)
			- B. Interview each student(loop)
				- B.1. *if* birthday exists in record, return found(**true**)
				- B.2. *else* add name and birthday to record(**false**)
			- C. Return **None** if last interviewed student without success
	- 📌Example of an algorithm correctness proof
		- To prove the correctness of [the last birthday matching problem](((631a1ab2-80b1-4c96-851e-295efa3cbfde))).
		- Following are the steps of proof on
			- 1. Induct on $k$: the number of students in the classroom
			- 2. **Hypothesis**: if first $k$ contains match, returns match(TRUE) before asking $k+1$ student
			- 3. **Base case**: $k=0$, first $k$ does not contain match
			- 4. Assume for induction hypothesis holds for $k = k'$, and consider $k = k' +1$ (saying in coding context, if not found, continue...)
			- 5. If first $k'$ contains a match, already returned a match by induction
			- 6. Else first $k'$ do not have match, so if first $k' +1$ has match, match contains $k' +1$
			- 7. Then algorithm checks directly whether birthday of student $k' +1$ exists in first $k'$
		- Side Note - $k'$​ is nothing else but an arbitrary number.
- ## ⌨Sample Code
	- 📌example code of [Solving birthday match in Python](((631a1ab2-80b1-4c96-851e-295efa3cbfde))).
		- ``` python
		  class StaticArray:
		          def __init__(self, n):
		                  self.data = [None] * n             # (0)Init
		                                                     
		                                                     # (1)get func
		          def get_at(self, i):
		                  if not (0 <= i < len(self.data)):      # check if the index i is valid
		                          raise IndexError
		                  return self.data[i]                    # get the data at index i
		  
		                                                     # (2)set func
		          def set_at(self, i, x):
		                  if not (0 <= i < len(self.data)):      # check if the index is valid
		                          raise IndexError
		                  self.data[i] = x                       # set the data at index i
		  
		  def birthday_match(students):
		          """
		          Find a pair of students with the same birthday
		          Input: tuple of student (name, bday) tuples
		          Output: tuple of student names or None
		          """
		          n = len(students)                                        # O(1)
		          record = StaticArray(n)                                  # O(n)
		          for i in range(n):                                       # n
		                  (name_que, bday_que) = students[i]               # O(1)
		                  for j in range(i):                               # k   check if it is in record
		                          (name_rec, bday_rec) = record[j]         # O(1)
		                          if bday_rec == bday_que:                 # O(1)
		                                  return (name_que, name_rec)      # O(1)
		                  record.set_at(i, (name_que, bday_que))           # O(1)
		          return None                                              # O(1)
		  
		  ```
- ## 🥼Expert's Advice
  See what experts addressed.
	- Francis Sullivan
		- For me, great algorithms are the poetry of computation. Just like verse, they can be terse, allusive, dense, and even mysterious. But once unlocked, they cast a brilliant new light on some aspect of computing.
	- Donald Knuth
		- An algorithm must be seen to be believed.
	- Linus Torvalds
		- I will, in fact, claim that the difference between a bad programmer and a good one is whether he considers his code or his data structures more important. Bad programmers worry about the code. Good programmers worry about data structures and their relationships.