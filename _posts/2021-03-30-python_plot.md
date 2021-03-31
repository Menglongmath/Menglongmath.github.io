---
layout: single
title: "Plot with python"
category:
  - Tutorial
tags:
  - python
#last_modified_at: 2016-03-09T16:20:02-05:00
excerpt: "Plot tips with python"
toc: true
toc_sticky: true
---



## Matplotlib
* Build a figure
```python
fig = plt.figure()  # an empty figure with no Axes.
```
or
```python
fig, ax = plt.subplots()  # Create a figure containing a single axes.
```
* Plot using `plt.plot()`, which automatically generates a figure and an axe with data on it.
```python
plt.plot([1, 2, 3, 4], [1, 4, 2, 3])  # Matplotlib plot.
```

* Plot using  `ax.plot()`, which will plot data on the axe `ax` and the current figure.
```python
ax.plot([1, 2, 3, 4], [1, 4, 2, 3])  # Plot some data on the axes.
```

* Set legends
```python
plt.plot([1,2,3], label='cubic')
plt.legend()
```
or
```python
ax.plot([1, 2, 3], label='Inline label')
ax.legend()
```


* Set title, x label, y label
```python
plt.xlabel('x label')
plt.ylabel('y label')
plt.title("Simple Plot")
```
or
```python
ax.set_xlabel('x label')  # Add an x-label to the axes.
ax.set_ylabel('y label')  # Add a y-label to the axes.
ax.set_title("Simple Plot")  # Add a title to the axes.
```

* Subplots
```python
plt.figure(figsize=(9, 3))
plt.subplot(131)
plt.bar(names, values)
plt.subplot(132)
plt.scatter(names, values)
plt.suptitle('Categorical Plotting')
plt.show()
```
or
```python
fig, axs = plt.subplots(2, 2)
axs[0, 0].plot(x, y)
axs[0, 0].set_title('Axis [0, 0]')
axs[0, 1].plot(x, y, 'tab:orange')
axs[0, 1].set_title('Axis [0, 1]')
axs[1, 0].plot(x, -y, 'tab:green')
axs[1, 0].set_title('Axis [1, 0]')
axs[1, 1].plot(x, -y, 'tab:red')
axs[1, 1].set_title('Axis [1, 1]')
```
* Customizing Figure Layouts Using GridSpec
```python
figure=plt.figure(figsize=figsize)
spec=gridspec.GridSpec(ncols=2, nrows=2, figure=figure)
for i in range(2):
    for j in range(2):
        ax=figure.add_subplot(spec[i,j])
        ax.set_xlabel('x')
        ax.set_ylabel('y')
        ax.plot(x,y,label='label')
        ax.legend()
```
or
```python
fig2 = plt.figure(constrained_layout=True)
spec2 = gridspec.GridSpec(ncols=2, nrows=2, figure=fig2)
f2_ax1 = fig2.add_subplot(spec2[0, 0])
f2_ax2 = fig2.add_subplot(spec2[0, 1])
f2_ax3 = fig2.add_subplot(spec2[1, 0])
f2_ax4 = fig2.add_subplot(spec2[1, 1])
```



* Hide x labels and tick labels for top plots and y ticks for right plots.
```python
for ax in axs.flat:
    ax.label_outer()
```
