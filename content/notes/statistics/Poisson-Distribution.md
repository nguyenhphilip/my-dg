---
title: Poisson Distribution
---

#flashcards 
Great source: The Poisson Distribution and Poisson Process Explained

---

# When to use it
When you want to model the _discrete_ counts of a process where the average time between events is known, but the exact timing of events is random. 

When you want to find the probability of observing a particular number of events in a time period or the probability of some waiting time until the next event

# Assumes
- That each event is independent of the last
- That we know the average time between events
- That we define an time-span (e.g. over 600 days)

# PMF
The probability of observing **k** events in a time period given the **duration of the time period** and the **average number of events per time is**: $$P(K \text{ events in interval}) = e^{-\lambda}{\frac{\lambda^k}{k!}}$$ where $\lambda$ is the rate parameter, which is a function of the number of average events per time, and the length of the time period. In words $\lambda$ is the expected number of events in one interval. 

$\lambda$ therefore, the expected number of events in a given interval, is the number of events with the greatest probability of observing.

Changing $\lambda$ changes the number of expected events per time interval. 

# An example

If we expect, say, 5 meteors per hour, on average, or 1 every 12 minutes, and we want to watch the meteor shower for one hour, then we can expect to see ==5== meteors in that duration. 
<!--SR:!2021-08-27,31,250--> 

Mathematically: $$\lambda = \frac{\text{num of events (meteors)}}{\text{duration of interval}}{\cdot}{\text{(total duration of meteor watching)}}$$ 

$$ = \frac{1 \text{ meteor}}{\text{12 minutes}}{\cdot}60\text{ minutes} = 5 \text{ meteors expected in 60 minutes of watching}$$

Then the probability of observing $k=3$ meteors in an hour is: $$P(k=3)=e^{-5}\frac{5^3}{3!}=0.14=\frac{1}{7}$$

So in a week, you'd expect to see 3 meteors in an hour of watching on one of those days.

# Waiting Times

The probability of waiting more than $t$ units of time follows a decaying exponential curve: $$P(T>t) = e^{-\frac{events}{time}\cdot{t}}$$