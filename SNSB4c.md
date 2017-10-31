

```python
import matplotlib.pyplot as plt
import numpy as np
from scipy import arange

```


```python
def q(p,x,l):
    return (np.exp(l*(p*x)))/(np.exp(l*(1-p))+np.exp(l*(p*x)))
```


```python
def p(q,l):
    return (np.exp(l*q))/(np.exp(l*q)+np.exp(l*(2-2*q)))  
```


```python
x=2
l=1
range_pq = arange(0,1,0.001)
psolve = 1-p(range_pq,l)
qsolve = q(range_pq,x,l)


plt.plot(psolve,range_pq,label='$p_L$')
plt.plot(range_pq,qsolve,label='$q_U$')
#plt.plot(qsolve-range_pq,range_pq,label='$q_U$')
plt.xlim(0,1.0)
plt.xlabel('$p_L$')
plt.ylabel('$q_U$')
plt.ylim(0,1.0)
plt.legend()
plt.savefig('plotSNSB1.png')

plt.show()


```


![png](https://raw.githubusercontent.com/joostbouten/assignments/master/output_3_0.png)


