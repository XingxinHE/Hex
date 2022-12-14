# 📝Definition
if $f$ is a function which is [[Continuous]] on the interval $[a,b]$ and $M$ lies between the value $f(a)$ and $f(b)$, then there is at least one point $c$ between $a$ and $b$ such that $f(c)=M$.
(A function is **continuous on a closed interval** [a,b] if it is right-continuous at a, left-continuous at b, and continuous at all points between a and b.)

# 📈Diagram
![Intermediate_Value_Theorem](../assets/Intermediate_Value_Theorem.png){:height 136, :width 222}

# ✒Descriptive Explanation
The Intermediate Value Theorem is <u>profound</u> because it <u>takes information that is local</u> by nature, and allows you to <u>conclude a global result</u>. [[continuity]] at a point is local information, because it only requires knowledge of the function's behavior near that point. But somehow, if we know this fact at every point on an interval, then the Intermediate Value Theorem tells us something about the overall, or global behavior - namely, that the function has to take on a particular value, or its graph has to cross a certain line.

# 🕳Pitfall
What should we be awared?
- 📌Suppose that $f(1)=2$ and $f(4)=4$ . Must the graph $f$ of intersect the line $y=3$?
    - diagram
      ![ascii_table](../assets/images_u0lim5_ivt2.svg){:height 136, :width 222}
    - answer:
        - Not necessarily. Because it doesn't say this is a continuous function. Therefore the following function need not to intersect with the line.
        - A diagram prove that.
          ![ascii_table](../assets/images_u0lim5_ivtsol2.svg){:height 136, :width 222}
        