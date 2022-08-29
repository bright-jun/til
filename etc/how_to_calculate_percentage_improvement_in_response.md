# How to calculate percentage improvement in response time

# 응답시간 절감율

$$
\cfrac{(time_{old} - time_{new})}{time_{old}} \times 100(\%)
$$

$**time_{old} = 10ms, time_{new} = 4ms**$

$**\cfrac{(10 - 4)}{10} \times 100 = 60\%$**

> There is a 60% reduction in time.
> 

# 성능 개선율

Performance is about how much can be done in the same amount of time.

$$
performance\propto\cfrac{1}{time}
$$

$$
\cfrac{(performance_{new} - performance_{old})}{performance_{old}} \times 100(\%) \\ = \cfrac{(time_{old} - time_{new})}{time_{new}} \times 100(\%)
$$

$**time_{old} = 10ms, time_{new} = 4ms**$

$**\cfrac{(10 - 4)}{4} \times 100 = 150\%**$

> There is a 150% increase in performance.
> 

# 성능 비교

$$
⁍
$$

$$
\cfrac{performance_{new}}{performance_{old}} = \cfrac{time_{old}}{time_{new}}
$$

$**time_{old} = 10ms, time_{new} = 4ms**$

$**\cfrac{10}{4} = 2.5$**

> Your new time is 2.5x faster.
>

# 참고

- [How to calculate percentage improvement in response time for performance testing](https://stackoverflow.com/a/53563651)
