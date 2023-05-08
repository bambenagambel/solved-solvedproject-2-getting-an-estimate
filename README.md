Download Link: https://assignmentchef.com/product/solved-solvedproject-2-getting-an-estimate
<br>
In many areas of mathematics and the sciences, there is a need to be able to provide an estimate of a value.For example, if you were watching the price fluctuation of a publicly traded stock or the price of a gallon of gas, you would want to know the average value.

For a set of 10 numbers: x = { 4, 2, 5, 3, 2, 4, 2, 6, 3, 4 }

we begin by adding all the numbers and dividing it by 10.We can generalize the process with a little math notation to represent the sum of the first n values of x.

The problem with taking an average using this equation is that the computation is basically a batch process. To add up all those numbers, you have to have all of them available. Depending upon the amount of historical data, this means that we must keep a potentially huge set of terms stored in memory.

So whatâ€&#x2122;s the big deal? There are many applications where we need to compute a running average for a large set of data over a period of time. For example, many cars now compute fuel economy over the long and short term. As one drives, new data is constantly becoming available.

Is there a better way? Of course. To see how, let’s look at how the average value changes as new data comes in. Let An be the mean (average) of the first n values of the set. As the data comes in, we’ll have:

-Or-

One will recognize that this can be rewritten as

As a result, to compute a running historical average, we only need to keep the previous summation and add to it the newly acquired data value. In other words, we keep a running sum.

For the set of numbers shown above, after the third number Sumn-1 is 11 and the average for the 4th is now (11 + 3)/4. Then the running sum becomes 14. Continuing, the 5th is (14 + 2)/5 and the running sum becomes 16.

There are two basic algorithms: 1) computing the sum, and 2) computing the average.

Compute Sum

1. Initially set sum and count to zero.2. Add the value of x to sum3. Add 1 to the n4. Repeat steps 2 and 3 whenever adding a new value x

ComputeAverage

1. Return sum divided by n;

We could easily do this with a loop setting sum = sum + x, but we want to be able to â€˜re-useâ€&#x2122; our code at some point in the future. For example, there are many applications where we need to compute several running averagesat the same time. Doing this in the traditional way can lead to having to remember the names of lots of variables or, in the worst case, having lots of duplicate code

We can easily get around this by developing a simple Object Oriented approach wherein we design the averaging method(s) using a container (an object) to think itâ€&#x2122;s computing only one average but we create multiple â€˜instancesâ€&#x2122; of the data. Think of it as having several cups. To each cup we deposit a coin and, when we want, for each cup we can count the total value of the coins and divide it by the number of coins to find the average coin value.

Consider the prototype provided below. Note that two variables, sum and n, have been defined. In an OOD approach, they will contain the data (running sum and count) for each â€˜instanceâ€&#x2122; â€“ one for sum1 and the other for sum2. To add 10.75 to sum1, one adds the statement:

sum1.add(10.75);

Similarly, when doing the same for sum2. Each instance of the Average class, sum1 and sum2, is a container holding its own running sum and count.

“`javapublic class Average{private double sum = 0;private int n = 0;

public static void main(String[] args){Average sum1 = new Average();Average sum2 = new Average();int i;double x;// Code to compute 20 random numbers and their running average// plus the running average of the first 20 integers (1-20)System.out.println(“Final averages: ” + sum1.getAverage()+ “, ” + sum2.getAverage());}

public void add(double x){

}

public void add(int x){

}

public double getAverage(){

}}“`

Modify the prototypeas follows:

Â· Complete the two â€œaddâ€� methods â€“ one that takes a double as a parameter to add real numbers and the second anintto add integers to the sum.Â· Complete the â€œgetAverageâ€� method that returns the current average (a double).Â· Add code in the main method (a loop) to add a randomly generated number (20.0*Math.random()+1) to sum1 and an integer in the range of 1-20 to sum2.Â· For each iteration of the loop, print the running average of each.Â· Finally, compare the two averages and print which is larger.

The prototype code should be considered only a starting point. Make sure your solution is thoroughly debugged.

The following specifications and guidelines also apply:

1. Make sure that your project meets all of the requirements set forth.2. Be sure that it has your name in it.All work must be original and your own! No credit will be given for plagiarized work.3. Even if you are not successful in completing the project, submit what you have as partial credit will be given for programs that would work if minor corrections in logic are made.4. No credit will be given for any work that is submitted late!