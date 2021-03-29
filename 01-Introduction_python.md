# Introduction to Python Programming

## Start Jupyter Notebook sessions


* If you are using a cloud-based service a Jupyter session will be started when you log on.
* If you have installed a Jupyter/Python distribution on your laptop then you can open a Jupyter session in one of two different ways:
  * Use the Anaconda Navigator App, or
  * open a terminal window on your laptop and execute the following statement at the command line:

  `$ jupyter notebook`

* Either way, once you have opened a session you should see a browser window like this:

















```python
#example 1
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
x1 = np.arange(-3.14, 3.14, 0.01)
x2 =np.arange(-3.14, 3.14,1)
y1 = np.sin(x) 
y2 = np.sin(x2)
plt.plot(x1, y1, 'r')
plt.scatter(x2,y2)
plt.show()
```
