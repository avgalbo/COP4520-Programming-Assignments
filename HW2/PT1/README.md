Anthony Galbo
Team 24
COP 4520 Spring 2022

Programming Assignment 2 Part 1

Source code name: BirthdayParty.java

## Compile and Run Instructions

1. In a terminal, navigate to the location of BirthdayParty.java using the command:
```bash
    cd
```
2. To compile the program, run the following command:
```bash
    javac BirthdayParty.java
```
3. To run the program, use the following command:
```bash
    java BirthdayParty <n>
```

Where ```<n>``` is a custom number of guests the user can provide in the command line.

If a user does not provide a number in the command line, the code will default the number of guests to 10.

## Output

The output will display to the console in the following format:

If a guest eats the cupcake, the console will display:
```txt
Guest Number: <GuestNum> has eaten the cupcake.
```

If a guest eats the cupcake, the console will display:
```txt
Guest Number: <GuestNum> has replaced the cupcake. <n> guests visited the labyrinth.
```

If a guest finishes the labyrinth, the console will display:
```txt
Guest Number: <GuestNum> finished labyrinth.
```

If all the guests finishes the labyrinth, the console will display:
```txt
All of the guests has visited the Minotaur’s labyrinth!
```

To time efficiency, the console will display:
```txt
Party Took 166ms to finish
```

## Proof of Correctness
This program utilizes the Java Semaphore lock class which will only allow 1 of the 10 guests to enter Minotaurs labyrinth at a time. When a guest enters the labyrinth, the Semaphore will acquire a permit and will release it only when a guest completes the labyrinth.

## Efficiency

Since there is no standard runtime for this algorithm. I am going to analyze this by a glance.

In the guest class each guest is in a loop until a guest breaks out of it.

So that runs in: ```O(n)``` time.

In the BirthdayParty class, each guest is called in a loop under the condition while each guest is in the party.

So that runs in: ```O(n)``` time.

With that said, it is my estimation that this algorithm runs in: ```O(n^2)``` time.


## Experimental evaluation

Before I display the results, This experiment was tested on an Macbook pro intel i9 processor with 16gb of ram.

Results may differ on machines with different cores.

I tested ten different test runs.

Trial 1 Run recorded at ```126ms```
Trial 2 Run recorded at ```109ms```
Trial 3 Run recorded at ```109ms```
Trial 4 Run recorded at ```149ms```
Trial 5 Run recorded at ```132s```
Trial 6 Run recorded at ```102ms```
Trial 7 Run recorded at ```161ms```
Trial 8 Run recorded at ```129ms```
Trial 9 Run recorded at ```159ms```
Trial 10 Run recorded at ```128ms```

On avg at ```130.4ms``` is a reasonable time for each guest on one thread and only allowing one guest to enter the labyrinth on each permit.  