# Save the trained scikit learn models with Python Pickle

Agenda is to save the trained model in local system as a black box and send this black box to where ever it need.

# Why we need to save the scikit learn models
Let’s understand the need to save the trained scikit learn models a bit more. In the learning phase of machine learning, we follow the below workflow to solve any machine learning project.

Machine Learning Project workflow
Getting the project related data from different sources.
Performing the data cleaning techniques on the data gathered.
Considering the split criteria (70% of training and 30% testing) to split the data into the training and testing datasets.
Using the training dataset to model any classification or clustering algorithm.
Using the trained model to predict the target class for test dataset.
If the trained model accuracy was not good enough, do changes in any of the above stages.

The last phase where we need to spend most of the time after the cleaning phase is to get the trained model which perform well enough to place in the production. This trained model testing won’t always be on the local system. In most of the cases, the performance of the trained model will calculate in the real environment.

# Why save the trained models?

Suppose we build an Email classification model to classify the email is Spam or Not for a free email service provider We may create the email spam identification model in our local system but classify every email hit to the user the modeled classifier needs to be on the production server or in interrelated to any app.

Even though the whole project is a python based. Still, we can’t run the models on the servers where the entire application frame working is running. So In such cases, we need to dump the modeled classifier. In plain words saying. If we dump the modeled classifier means we are storing the coefficients and some related information of the modeled classifier.

In the next step, we need to load the dumped model where it is required. Once we successfully loaded the previously dumped model, then the classification of the email should happen without any issues. So in the situation like these, we need to figure out a way to dump the trained models and to use them whenever and where ever it required.

# Methods to save the scikit learn models
The modern ways to save the trained scikit learn models is using the packages like

* Pickle (Python Object Serialization Library)
* Joblib (One of the scikit-learn Method)
Before learning how to save the trained models. In this article, we are going to cover only about the Pickle library. 
Let’s first understand about the functionality of the Pickle library. Then we learn how to save the scikit-learn models and loading them back to as same as the previously modeled models.

# What is Pickle?
Pickle is one of the Python standard libraries. Which is so powerful and the best choice to perform the task like

* Serialization
* Marshalling
The above two functionalities are popularly known as  Pickling and Unpickling

* Pickling
- Pickling is the process converting any Python object into a stream of bytes by following the hierarchy of the object we are trying to convert.
* Unpickling
- Unpickling is the process of converting the pickled (stream of bytes) back into to the original Python object by following the object hierarchy
The objects can be anything. Suppose we perform the python pickling on a python list or dictionary object also. Below is the list of what kind of objects can pickle and what kind of objects should not pickle.

# What can Pickle and what can’t Pickle in Python
## What can Pickle
* All number related data types and the complex number data type too.
* The Boolean kind of data type.
* Python string, list, tuple, dictionaries.
* Built-in function and object classes.
## Whan can’t Pickle
* Pickle already pickled python object
* Pickle high recursive Python objects

# Python Pickle Examples
Before we pickle the scikit learn models. Let’s quickly see an example on how to pickle and unpickle the Python list objects.

Pickle the Python List object
import pickle
 
# pickle list object

Python Code: 
numbers_list = [1, 2, 3, 4, 5]
list_pickle_path = 'list_pickle.pkl'
 
#Create an variable to pickle and open it in write mode
list_pickle = open(list_pickle_path, 'wb')
pickle.dump(numbers_list, list_pickle)
list_pickle.close()

* Importing the Python Standard serialization package pickle.
* Creating the python list object with 1 to 5 numbers.
* Given the path to store the numbers list pickle (‘list_pickle.pkl’)
** Open the list_pickle in write mode in the list_pickle.pkl path.
** Use the dump method in pickle with numbers_list and the opened list_pickle to create pickle
** Close the created pickle.
