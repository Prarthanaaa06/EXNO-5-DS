# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

# Aim:
  To Perform Data Visualization using matplot python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
 import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from scipy.interpolate import make_interp_spline

sns.set_theme(style="darkgrid")

x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]

plt.figure(figsize=(8, 5))

x1, y1 = [1, 2, 3], [2, 4, 1]
x2, y2 = [1, 2, 3], [4, 1, 3]

plt.plot(x1, y1, label="Line 1", color="blue", marker="o", linewidth=2)
plt.plot(x2, y2, label="Line 2", color="orange", marker="s", linewidth=2)

plt.xlabel("X Axis")
plt.ylabel("Y Axis")
plt.title("Multi-Line Graph")
plt.legend(loc="upper right")

plt.show()
<img width="706" height="440" alt="image" src="https://github.com/user-attachments/assets/3a7d563a-4674-4318-a224-75f906ebf164" />

plt.figure(figsize=(8, 5))

x_vals = [0, 1, 2, 3, 4, 5]
y_vals = [0, 1, 4, 9, 16, 25]

plt.plot(x_vals, y_vals, color="purple", alpha=0.7, linewidth=2)
plt.fill_between(x_vals, y_vals, color="purple", alpha=0.3, label="Area under curve")

plt.xlabel("X Values")
plt.ylabel("Y Values")
plt.title("Line Graph with Fill Between")
plt.legend()
plt.show()
<img width="835" height="533" alt="image" src="https://github.com/user-attachments/assets/a41c8266-9e2b-4121-95ac-a694ccf4e9e3" />

plt.figure(figsize=(8, 5))

x_arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
y_arr = np.array([2, 4, 5, 7, 8, 8, 9, 10, 11, 12])

x_smooth = np.linspace(x_arr.min(), x_arr.max(), 300)
spline = make_interp_spline(x_arr, y_arr, k=3)
y_smooth = spline(x_smooth)

plt.scatter(x_arr, y_arr, color="red", label="Original Data")
plt.plot(x_smooth, y_smooth, color="green", label="Cubic Spline Interp.")

plt.xlabel("X")
plt.ylabel("Y")
plt.title("Cubic Spline Interpolation Curve")
plt.legend()
plt.show()
<img width="831" height="528" alt="image" src="https://github.com/user-attachments/assets/695e08bf-e8b2-4cb5-9069-758d515978a0" />

plt.figure(figsize=(8, 5))

values = [5, 6, 3, 7, 2]
names = ["A", "B", "C", "D", "E"]
colors_list = ['red', 'green', 'blue', 'orange', 'purple']

plt.bar(names, values, color=colors_list, edgecolor='black')

plt.xlabel("Categories")
plt.ylabel("Values")
plt.title("Categorical Bar Chart")
plt.show()
<img width="814" height="538" alt="image" src="https://github.com/user-attachments/assets/823ea96b-cc68-4e8c-8b73-daf98d36fc05" />

df = sns.load_dataset("tips")

avg_data = df.groupby('day', observed=False)[['total_bill', 'tip']].mean()

plt.figure(figsize=(8, 6))

p1 = plt.bar(avg_data.index, avg_data['total_bill'], label='Total Bill', color='orange')
p2 = plt.bar(avg_data.index, avg_data['tip'], bottom=avg_data['total_bill'], label='Tip', color='yellow')

plt.xlabel('Day of the Week')
plt.ylabel('Amount ($)')
plt.title('Average Total Bill and Tip by Day (Stacked)')
plt.legend()
plt.show()
<img width="854" height="615" alt="image" src="https://github.com/user-attachments/assets/494bcfc2-444a-48a0-82a5-a90e9edc980b" />

plt.figure(figsize=(8, 5))

x_scatter = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
y_scatter = [2, 4, 5, 7, 6, 8, 9, 11, 12, 12]

plt.scatter(x_scatter, y_scatter, label="stars", color="blue", marker="*", s=150, edgecolor='black')

plt.xlabel("X Axis Values")
plt.ylabel("Y Axis Values")
plt.title("Scatter Plot with Star Markers")
plt.legend()
plt.show()
<img width="855" height="537" alt="image" src="https://github.com/user-attachments/assets/30713799-1ffc-4a4d-8983-b25a63643b49" />


plt.figure(figsize=(6, 6))

activities = ['eat', 'sleep', 'work', 'play']
slices = [3, 7, 8, 6]
colors = ['crimson', 'gold', 'forestgreen', 'royalblue']

plt.pie(slices, labels=activities, colors=colors, startangle=90, shadow=True, autopct='%1.1f%%', explode=(0, 0, 0.1, 0))

plt.title("Daily Activity Allocation")
plt.show()
<img width="852" height="645" alt="image" src="https://github.com/user-attachments/assets/15746f55-8f7c-4a28-9d81-4a5c0363bbeb" />

# Result:
The graphs and plots were neatly interpolated and visuvalised. 
