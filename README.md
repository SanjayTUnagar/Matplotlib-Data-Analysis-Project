# Matplotlib — Complete Python Data Visualization Guide

Matplotlib is a powerful Python library used for **data visualization**. It provides a wide range of static, animated, and interactive plots.

## 🔑 Key Features

- Simple & easy to use
- Widely used for 2D plots
- Highly customizable
- Works well with NumPy, Pandas
- Publication quality figures

## 🔄 Basic Workflow

```
Prepare Data → Create Plot → Customize Plot → Display Plot
```

---

## 📦 Importing Library

```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
```

> **Note:** `pyplot` is a submodule of Matplotlib used for plotting.

---

## 🧱 Basic Plot Syntax

```python
plt.plot(x, y)
plt.title('Title')
plt.xlabel('X axis')
plt.ylabel('Y axis')
plt.grid(True)
plt.show()
```

---

## 📚 Table of Contents

1. [Line Plot](#1-line-plot)
2. [Bar Chart](#2-bar-chart)
3. [Scatter Plot](#3-scatter-plot)
4. [Histogram](#4-histogram)
5. [Pie Chart](#5-pie-chart)
6. [Area Plot](#6-area-plot)
7. [Subplots (Multiple Plots)](#7-subplots-multiple-plots)
8. [Customization Options](#8-customization-options)
9. [Commonly Used Functions](#9-commonly-used-functions)
10. [Advanced Plot Examples](#10-advanced-plot-examples)
11. [Working with Pandas](#11-working-with-pandas)
12. [Complete Program Example](#12-complete-program-example)
13. [Mini Project: Weekly Sales Tracker](#13-mini-project-weekly-sales-tracker)
14. [Tips & Best Practices](#14-tips--best-practices)

---

## 1. Line Plot

Shows relationship between two continuous variables.

```python
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y, marker='o', color='blue')
plt.title('Line Plot')
plt.xlabel('X axis')
plt.ylabel('Y axis')
plt.grid(True)
plt.show()
```

---

## 2. Bar Chart

Compare values across categories.

```python
categories = ['A', 'B', 'C', 'D']
values = [10, 20, 15, 25]

plt.bar(categories, values, color='skyblue', edgecolor='black')
plt.title('Bar Chart')
plt.xlabel('Categories')
plt.ylabel('Values')
plt.show()
```

---

## 3. Scatter Plot

Relationship between two variables using dots.

```python
x = [1, 2, 3, 4, 5]
y = [5, 3, 6, 2, 7]

plt.scatter(x, y, color='green', s=60)
plt.title('Scatter Plot')
plt.xlabel('X axis')
plt.ylabel('Y axis')
plt.show()
```

---

## 4. Histogram

Shows distribution of continuous data.

```python
data = [2, 3, 4, 5, 6, 6, 7, 8, 8, 9, 9, 10, 11, 12]

plt.hist(data, bins=5, color='violet', edgecolor='black')
plt.title('Histogram')
plt.xlabel('Values')
plt.ylabel('Frequency')
plt.show()
```

---

## 5. Pie Chart

Shows percentage distribution.

```python
labels = ['A', 'B', 'C', 'D']
sizes = [30, 20, 25, 25]

plt.pie(sizes, labels=labels, autopct='%1.1f%%',
        colors=['gold', 'lightblue', 'lightgreen', 'pink'])
plt.title('Pie Chart')
plt.show()
```

---

## 6. Area Plot

Shows cumulative value under the line.

```python
x = [1, 2, 3, 4, 5]
y = [1, 4, 2, 5, 3]

plt.fill_between(x, y, color='orange', alpha=0.5)
plt.plot(x, y, color='red', marker='o')
plt.title('Area Plot')
plt.show()
```

---

## 7. Subplots (Multiple Plots)

Display multiple plots in a single figure.

```python
import numpy as np

x = np.arange(1, 6)
y = x * 2

plt.subplot(1, 2, 1)
plt.plot(x, y, 'bo-')
plt.title('Line')

plt.subplot(1, 2, 2)
plt.bar(x, y, color='green')
plt.title('Bar')

plt.tight_layout()
plt.show()
```

---

## 8. Customization Options

```python
plt.plot(x, y,
         color='red',        # Color
         linestyle='--',     # Line Style
         marker='o',         # Marker
         linewidth=2)        # Line Width

plt.grid(True)               # Grid
plt.legend()                 # Legend
plt.figure(figsize=(6, 4))   # Figure Size
plt.savefig('plot.png')      # Save Figure
```

### Line Styles

| Style | Description |
|---|---|
| `-` | Solid |
| `--` | Dashed |
| `:` | Dotted |
| `-.` | Dash-Dot |

### Markers

| Marker | Shape |
|---|---|
| `o` | Circle |
| `s` | Square |
| `^` | Triangle |
| `*` | Star |

---

## 9. Commonly Used Functions

| Function | Description |
|---|---|
| `plt.plot()` | Line plot |
| `plt.bar()` | Bar chart |
| `plt.scatter()` | Scatter plot |
| `plt.hist()` | Histogram |
| `plt.pie()` | Pie chart |
| `plt.fill_between()` | Area plot |
| `plt.subplot()` | Multiple plots |
| `plt.title()` | Add title |
| `plt.xlabel()` | X axis label |
| `plt.ylabel()` | Y axis label |
| `plt.show()` | Display plot |

---

## 10. Advanced Plot Examples

### Box Plot

```python
data1 = [65, 70, 75, 80, 85, 90]
data2 = [55, 60, 65, 70, 75, 95]
data3 = [70, 75, 80, 82, 88, 92]

plt.boxplot([data1, data2, data3])
plt.xticks([1, 2, 3], ['Set 1', 'Set 2', 'Set 3'])
plt.ylabel('Values')
plt.title('Box Plot')
plt.show()
```

### Heatmap (Using imshow)

```python
import numpy as np

data = np.random.rand(6, 6)

plt.imshow(data, cmap='coolwarm')
plt.colorbar()
plt.title('Heatmap')
plt.show()
```

### 3D Plot (mplot3d)

```python
from mpl_toolkits import mplot3d
import numpy as np

fig = plt.figure()
ax = plt.axes(projection='3d')

x = np.linspace(-5, 5, 50)
y = np.linspace(-5, 5, 50)
X, Y = np.meshgrid(x, y)
Z = np.sin(np.sqrt(X**2 + Y**2))

ax.plot_surface(X, Y, Z, cmap='viridis')
ax.set_title('3D Plot')
plt.show()
```

### Polar Plot

```python
import numpy as np

theta = np.linspace(0, 2 * np.pi, 100)
r = np.abs(np.sin(2 * theta))

plt.polar(theta, r)
plt.title('Polar Plot')
plt.show()
```

### Bubble Chart

```python
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 8, 4]
size = [100, 300, 200, 500, 400]

plt.scatter(x, y, s=size, color='purple', alpha=0.6)
plt.title('Bubble Chart')
plt.xlabel('X axis')
plt.ylabel('Y axis')
plt.show()
```

---

## 11. Working with Pandas

```python
import pandas as pd

df = pd.read_csv('data.csv')

plt.plot(df['X'], df['Y'], 'g-o')
plt.title('Data from Pandas')
plt.xlabel('X')
plt.ylabel('Y')
plt.show()
```

---

## 12. Complete Program Example

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [3, 1, 4, 2, 5]

plt.figure(figsize=(6, 4))
plt.plot(x, y, marker='o', color='purple', linewidth=2)
plt.title('My First Plot')
plt.xlabel('X axis')
plt.ylabel('Y axis')
plt.grid(True)
plt.show()
```

---

## 13. Mini Project: "Weekly Sales Tracker"

**Goal:** Use a simple line and bar chart together to track a week of sales — a beginner-friendly project combining several concepts from this guide.

```python
import matplotlib.pyplot as plt

# Step 1: Data
days = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
sales = [200, 250, 180, 300, 280, 350, 320]

# Step 2: Create the figure
plt.figure(figsize=(8, 5))

# Step 3: Plot as a line with markers
plt.plot(days, sales, marker='o', color='blue', linewidth=2)

# Step 4: Add labels and title
plt.title('Weekly Sales Tracker')
plt.xlabel('Day')
plt.ylabel('Sales ($)')
plt.grid(True)

# Step 5: Highlight the best day
best_day = sales.index(max(sales))
plt.scatter(days[best_day], sales[best_day], color='red', s=100, zorder=5)
plt.text(days[best_day], sales[best_day] + 15, 'Best Day!', ha='center', color='red')

# Step 6: Save and show
plt.savefig('weekly_sales.png')
plt.show()

# Step 7: Print a quick summary
print(f"Total Sales: ${sum(sales)}")
print(f"Average Sales: ${sum(sales)/len(sales):.2f}")
print(f"Best Day: {days[best_day]} (${sales[best_day]})")
```

**What this project demonstrates:** basic line plotting, markers, titles/labels, highlighting a specific data point with `scatter()` + `text()`, and saving a chart with `savefig()` — a simple, complete beginner project using only Matplotlib.

---

## 14. Tips & Best Practices

- ⭐ Use meaningful titles and labels
- ⭐ Use grids for better readability
- ⭐ Choose the right type of plot for your data
- ⭐ Keep your visualization simple and clean
- ⭐ Save your figures in high quality (`plt.savefig()`)

---

---

# 👨‍💻 Author

**Sanjay Unagar**

Data Analyst | Python | SQL | Excel | Power BI | Data Visualization

🔗 GitHub:  
https://github.com/SanjayTUnagar

🔗 LinkedIn:  
https://www.linkedin.com/in/sanjayunagar/

---

# ⭐ Support

If you found this project useful, please consider giving it a ⭐ on GitHub.

---
