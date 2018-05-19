#matplotlib_learn
#Add import codecademylib to the top of script.py. This will allow for your plots to render in our browser.
import codecademylib
#We have provided some data in different lists in script.py. Look through these lists and try to understand what each one represents.
from matplotlib import pyplot as plt

months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]

visits_per_month = [9695, 7909, 10831, 12942, 12495, 16794, 14161, 12762, 12777, 12439, 10309, 8724]

#numbers of limes of different species sold each month

key_limes_per_month = [92.0, 109.0, 124.0, 70.0, 101.0, 79.0, 106.0, 101.0, 103.0, 90.0, 102.0, 106.0]
persian_limes_per_month = [67.0, 51.0, 57.0, 54.0, 83.0, 90.0, 52.0, 63.0, 51.0, 44.0, 64.0, 78.0]
blood_limes_per_month = [75.0, 75.0, 76.0, 71.0, 74.0, 77.0, 69.0, 80.0, 63.0, 69.0, 73.0, 82.0]


# create your figure here
# Create a figure of width 12 and height 8.
plt.figure(figsize=(12, 8))

#In the left subplot, we are going to plot the total page visits over the past year as a line.
#First, let's create the list of x-values, which is range(len(months)). Store this in a variable called x_values.
#Make sure this happens after the line where you created ax1, but before the line where you've created ax2, so that the plot goes in the subplot on the left.
#Plot the total page visits against these x_values as a line.
#Give the line markers that will help show each month as a distinct value.
#Label the x-axis and y-axis with descriptive titles of what they measure.
#Set the x-axis ticks to be the x_values.
#Label the x-axis tick labels to be the names stored in the months list.

ax1 = plt.subplot(1,3,1)
x_values = range(len(months))
plt.plot(x_values, visits_per_month, marker= "o")
plt.xlabel("Month")
plt.ylabel("Number of Page Visits")
plt.title("Page Visits Per Year")
ax1.set_xticks(x_values)
ax1.set_xticklabels(months)
plt.savefig("Site Visits.png")


#Write the command to create the right subplot (the one that would correspond to the plot with a square in our example figure).
#Save this subplot in a variable called ax2
#In the subplot on the right, we are going to plot three lines on the same set of axes. The x-values for all three lines will correspond to the months, so we can use the list of x_values we used for the last plot.
#On one plot, create the three lines:
#-number of key limes sold vs x_values
#-number of Persian limes sold vs x_values
#-number of blood limes sold vs x_values
#Make sure this happens after the line where you created ax2, so that it goes in the subplot on the right.
#Give each line a specific color of your choosing.
#Add a legend to differentiate the lines, labeling each lime species.
#Set the x-axis ticks to be the x_values, and the tick labels to be the months list.

ax2 = plt.subplot(1,3,2)
x_values = range(len(months))
plt.plot(x_values, key_limes_per_month, color="pink", marker='o')
plt.plot(x_values, persian_limes_per_month, color="blue", marker='o')
plt.plot(x_values, blood_limes_per_month, color='green', marker='o')
plt.legend(["Key Limes", "Persian Limes", "Blood Limes"], loc=4)
plt.xlabel("Month")
plt.ylabel("Number of Limes Sold")
plt.title("Limes Sold Per Year")
ax2.set_xticks(x_values)
ax2.set_xticklabels(months)
plt.savefig("Lime Sales.png")

plt.subplots_adjust(wspace=0.5)
plt.show()
