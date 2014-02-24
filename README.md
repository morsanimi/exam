import numpy as np
from matplotlib import pyplot as plt
import matplotlib.mlab as mlab
x,y,z=np.loadtxt('RR.rea',unpack=True)
a = 0
print('the invalid lines are')
for i in range(len(z)):
    if z[i]==1:
        a=a+1
        print i
print('in total there are'),a, ('lines')
#print y
print ('The maximum intensity is in place'), np.argmax(y)
#so far i have found the invalid lines and their number

#B
y2=y
for i in range(len(y2)):
    if z[i] == 1:
        y2=np.delete(y2,i)
print('done')
print('The minimum value is'),min(y2)
print('The maximum value is'),max(y2)
print('The median is'),sorted(y2)[len(y2)//2]
print('The standard deviation is'),np.std(y2)
print('The average value is'), np.average(y2)

#D
d = np.argmax(y2)
e = np.argmin(y2)
#mu = 100 # mean of distributionnp.average(y2)
#sigma = np.std(y2)
print d, e
plt.hist(y2)
#num_bins = 50
#n, bins, patches = plt.hist(y2, num_bins, normed=1, facecolor='green', alpha=0.5)
#y15 = mlab.normpdf(bins, mu, sigma)
#plt.plot(bins,y15)
plt.text(724,52500,'/ maximum')
plt.text(1100,1000,'/ minimum')
plt.title('Histogram of the cardiogram')
plt.show()

print y2
