---
layout: post
---
# **Machine learning for Newbie**
  <img src="assets/ml1.png">
  
  This article is for newbies first starting with machine learning. The idea in this article is to give a rough framework on     how and why should we start to learn machine learning and what are resources or platform from where one can start to learn.   This article will also cover some basic concepts in machine learning.

## **What is machine Learning**:
  The most formal definition of machine learning is “the field of study that gives computer ability to learn without being       explicitly programmed”. The process of learning involves training data and find pattern or make better decision based on       data provided.

## **Why Machine learning**:
  Machine learning is being used for decades but now it has gained more popularity, since the growth in use of artificial       intelligence in all field. With the evolution of artificial intelligence we can say that, if we don’t train ourselves then     machine is going to replace our work. AI is everywhere, we are always using it in some way without even knowing it. With the   growth in data in all fields, it impossible to understand and find pattern in data and data computing. This is where machine   learning has come into action. With help of machine learning algorithms it’s easy to understand and find pattern in data. We   can find use of machine learning everywhere. Below are some examples:

   **1. Spam filter in mail**: The way our spam filter work in gmail to classify mail as ‘spam’ or not ‘spam’.
  
   **2. Recommendation system like in Netflix and amazon**: Recommending products and movie based on user interest and                activity.
  
   **3. Online customer help by use of chatbots**: User support on various website using chatbots are life saviour.
  
   **4. Search engine result refining**: Using machine learning algorithm to refine search result to get good and relevant            content in search.
  
   **5. Virtual personal assistant (Siri, Alexa)**: AI assistants, understand voice commands and performs user’s tasks.
  
   **6. Fraud detection**: Based on transaction details classify if a transaction if legit or fraudulent.

### **Prerequisites**:
  Since you know what is machine learning and what’s the use of it, next question will come to your mind what do I need to       start?

  You need good knowledge and interest in mathematics if you want to learn machine learning.You should have good knowledge in:

  **1. Calculus**: You don’t need to know whole calculus, only concepts to find derivatives. You can find video on calculus           derivative on [khan academy](https://www.khanacademy.org/math/calculus-1/cs1-derivatives-definition-and-basic-rules).
 
  **2. Statistics**: To start with ML you should have a good knowledge of probability, mean, normal distribution, standard           deviation. There is a very good course on [statistics on Udacity](https://in.udacity.com/course/statistics--   st095)         which covers all the basic concepts in statistics.
 
  **3. Linear algebra**: Well in linear algebra we all know about matrices, scalar, vector, how to multiply matrices and how          to get transpose. If you don’t know you can revise your concepts from here [Matrices](https://www.khanacademy.org/math/precalculus/precalc-matrices), [vectors](https://www.khanacademy.org/math/precalculus/vectors-precalc).
 
  **4. Data analysis**: You need to know data interpretation, presentation and organisation of data, a course on [statistics on Udacity](https://in.udacity.com/course/statistics--st095) covers this concept.
 
  **5. Programming language**:
      Python is heavily being used for data science and R is also the second most famous language used in data science.Other         than Python and R, javascript, Ruby, java, c/c++ , Matlab and octave are being used to do program in machine learning.

  You don’t need to be great at these concepts or language, if only you know the basic concepts you can easily start.

### **Resources for machine learning**:
  You can always start learning from courses on [machine learning](https://www.coursera.org/learn/machine-learning) by “Andrew    ng” or [intro to machine learning](https://in.udacity.com/course/intro-to-machine-learning--ud120-india) by “Katie Malone”    and “Sebastian Thrun”. You can also do courses [statistics by SJSU](https://in.udacity.com/course/statistics--st095) to        have some basic knowledge in data representation and analysis. One can also start from this book [“The Elements of   Statistical Learning”](https://web.stanford.edu/~hastie/Papers/ESLII.pdf).

  Now we know what is machine learning, why it’s being used and from where we can start learning, let’s dive into some basic     concepts in machine learning.

## Machine learning types:
  Machine learning can be mainly categorised into 3 types.
  
  <img src="assets/type_machine.png">
  
  
   **1. Supervised learning**: In supervised learning we already know what our output is going to be assuming there is                 relation between input and output. We have given a input variable ‘X’ and output variable ‘Y’ and there is a mapping           function which we called hypothesis h(x) which maps our input variable to our output variable. The goal is to find             such a hypothesis which covers well our training data and can predict output if we provide new data.Supervised                 learning can be classified into two types:

   **1.1. Regression**: Mapping input variable to a continuous output variable, output is continuous in Regression. i.e Given           size and price of house predict price of houses, Predict age of a person based on a given picture of them.
  
   **1.2. Classification**: Given a training data set we have to classify new data based on our prediction, Output is discrete           in classification.i.e Based on training data classify if a cancer is benignant or malign, or classify if a mail is             spam or not.
  
  Since Regression and classification is a vast concept, I will cover them in more detail in next story.

   **2. Unsupervised Learning**: We don’t know what our output is going to be in unsupervised learning, we can derive                 structure from the data using relationship between the data.

   **2.1. Clustering**: It is famous algorithm in unsupervised learning, we try to find structure in data by creating cluster            using relations between data. i.e take a collection of 1,000,000 different genes, and find a way to automatically              group these genes into groups that are somehow similar or related by different variables, such as lifespan,                    location, roles, and so on.(example from coursera)

   **2.2. Non-clustering**: The “Cocktail Party Algorithm”, allows you to find structure in a chaotic environment. (i.e.                identifying individual voices and music from a mesh of sounds at a cocktail party).(example from coursera)

   **3. Reinforcement Learning**: Reinforcement learning is about taking best decision in a particular situation. In the below        figure there is a robot and a reward(Diamond) and the goal of the robot is to find the diamond using best possible path        and avoid fire. The robot will try all possible path to reach the diamond and will learn from the experience , each            positive path will add to the reward and negative will subtract from the reward. Total reward for the robot will be            calculated when it reaches the diamond.
   <img src="assets/re.png">
       
       
   **3.1. Positive Reinforcement**: Event which increase the Frequency of rewards i.e increase the performance.
   
   **3.2. Negative Reinforcement**: Event which increase the behaviour because a negative condition is avoided or stopped. i.e          provide enough to meet minimum behaviour.

That’s all folks for this story, I hope you found it useful. I will cover supervised learning algorithms and reinforcement machine learning in detail in separate story.This story is also published [here](https://medium.com/@kriti_shrivastwa/machine-learning-for-newbie-f79407ab378b) on medium.
