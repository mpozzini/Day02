# Day02_Lab
Code from day02 lab
# CS 167 Machine Learning
# Day 2 exercises
# note that each of these segments should be run in a different cell 
# within an iPython Notebook

#####
a=10
b=3.14
c = "machine learning"
d = 'hi'
e = 'x'
f = [1,2,3]
print(a,b,c,d,e,f)

#####

print("a's type:", type(a))
a = 'variables can change types'
print("a's type:", type(a))
print(type(b))
print(type(c))
print(type(d))
print(type(e))
print(type(f))

#####

x = [1,2,3] 
y=x
x[0] = "abc" 
print(y) 
#before you run, what will the value of y[0] be?

#####

z = x[1]
x[1] = "what"
print(x)
print(z)
x.append(70)
x.insert(2,90)
print(x)
#can you predict what will be output?

#####

print( x.index(90) )
print( len(x) )
print( x+x )
#can you predict what will be output?

#####
#List Slices 

my_list = [33, 55, 'hello','R2D2',7.8,'banana']
print( my_list[1:5] )
print( my_list[:4])
print( my_list[4:])
print( my_list[:])

#####

my_slice = my_list[1:5]
my_slice[2] = 'what'
print(my_slice)
print(my_list)
print(my_list[1:5] + 2*['Drake','University'])
my_list[:0] = ['Bulldogs']
print(my_list)
# why isn't "Drake" or "University" printed out in this last line?

#####

my_list = [42, 3.14, 'hello', ['ice', 'ice', 'baby']]
print(my_list[3][2])
print(my_list[2][1])
# wait, what? 
# explain what is happening here

#####
# In Python, a tuple is a collection which is ordered andÃ‚Â unchangeable. 
# In Python tuples are written with round brackets.

my_tuple = (100,200,'300')
print(my_tuple[1])
my_dictionary = {'x':42, 'y':3.14}
print(my_dictionary['x'])

#####

# Each of these lines will cause an error. 
# Can you describe why before running them one at a time?

print(my_list[1][2])
my_tuple[1] = 0
print(my_dictionary[1])

#####
# If statements and for loops
x = int(input())
if x < 0:
    print("x is negative")
elif x % 2:
    print("x is positive and odd")
else:
    print("x is even and nonnegative")

num_list = [3, 7, 9,17, 2]
for num in num_list:
    print(num)

print(range(10,20))
for n in range(10,20):
    print(n)

####
# iterating Through Data
my_data = [5.3, 3.2, 4.1, 5.9, 6.7, 3.5]
# method 1
for element in my_data:
    print(element)

# method 2
for idx in range(len(my_data)):
    print(my_data[idx])

#####
# Explain why these won't work:
my_data = [5.3, 3.2, 4.1, 5.9, 6.7, 3.5]
for i in my_data:
    print( my_data[i] )

for i in range(len(my_data)):
    print( i )

for i in range(my_data):
    print( my_data[i] )

#####
import pandas

#####

import pandas as pd
# The first step is to mount your Google Drive to your Colab account. 
#You will be asked to authorize Colab to access your Google Drive. Follow the steps they lead you throuh.

from google.colab import drive
drive.mount('/content/drive')

#####

#Download the restaurant data (it's in Blackboard under 'datasets'), and put it in your Google Drive. Make a note of the path
#I would suggest creating a datasets folder somewhere easy to get to, we'll be using this a lot.
# your path will look like '/content/drive/MyDrive/....wherever you put the data'

#change the following line so that it points to where you put restaurant.csv.
data = pd.read_csv('/content/drive/MyDrive/CS167_S21/CS167_datasets/restaurant.csv')
data.head()

#####

print(data['price'])

#####

print(data.loc[3])

#####

print(data.loc[3, 'type'])

#####

print(data.loc[3, 'type'])

#####

print(data.iloc[3,8])

#####

print(data.iloc[3][8])

#####

print(data.iloc[3])

#####

print(data['est'])

#####

data.loc[5]

#####

print(type(data))
print(type(data['est']))
print(type(data.loc[0]))
print(type(data.iloc[3,8]))

#####

data1 = pd.read_csv('/content/drive/MyDrive/CS167_S21/CS167_datasets/irisData.csv')
data1.head()

#####

type(data1['sepal length'].loc[0])

#####

data.iloc[3:6, 4:8]

#####

print(data['rain'].iloc[4])

#####

print(data['type']=='Thai')

#####

print(data[ data['type'] == 'Thai'])
