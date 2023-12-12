Assume that there are k allocation sequences in flexlayout, and there are $m_1,m_2,...,m_k$ elements in each allocation. Then the worst complexity of the old algorithm is $$O(\sum_{i=1}^k\frac{m_k*(m_k + 1)}{2})$$

![Alt text](./image.png)

obviously:

$$
\sum_{i=1}^k\frac{m_k*(m_k + 1)}{2} \leq \frac{n*(n + 1)}{2}
$$

So the complexity of the old algorithm is $O_{old} = O(n^2)$ 。

The complexity of the new algorithm at the position in the graph is also $O(\frac{m_k*(m_k + 1)}{2})$ :

![Alt text](./image-1.png)

When k=1. Complexity is $2 * O(\sum_{i=1}^k\frac{m_k*(m_k + 1)}{2}) = O(n*(n + 1)) = O(n^2)$

When $k\geq 2$, this will bring an additional constant complexity multiplier

![Alt text](./image-2.png)

The complexity is

$$
\begin{aligned}
3* O(\sum_{i=1}^k\frac{m_k*(m_k + 1)}{2}) &= \frac{3}{2}* O(\sum_{i=1}^km_k^2 + \sum_{i=1}^km_k) \\
&=\frac{3}{2}\*O(\sum_{i=1}^km_k^2 + n) \\
&\leq \frac{3}{2}O(n^2+n) \\
&=3*O_{old} \\
\end{aligned}
$$

The constant multiple calculation here is not rigorous, but in the end it can be seen that the optimization coefficient levels are similar. So I think the final conclusion is that the possible complexity increase brought by the new algorithm can be ignored.
