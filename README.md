# Single server with infinite capacity (M/M/1):(oo/FIFO)
## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 12 seconds, serivice time of lathe machine follows exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](1.png)

This is a queuing model in which the arrival is Marcovian and departure distribution is also Marcovian,number of server is one and size of the queue is also Marcovian,no.of server is one and size of the queue is infinite and service discipline is 1st come 1st serve(FCFS) and the calling source is also finite.

## Procedure :

![imAGE](2.png)



## Experiment:

![318827584-a5996c28-3cc0-4db1-a30e-7e00c3f133b7](https://github.com/user-attachments/assets/d01fad40-4d25-4eda-a930-787cb1859973)

 
## Program:

```py
arr_time = float(input("Enter the mean inter-arrival time of objects from Feeder (in secs): "))
ser_time = float(input("Enter the mean inter-service time of Lathe Machine (in secs): "))
Robot_time = float(input("Enter the additional time taken for the Robot (in secs): "))


lam = 1 / arr_time
mu = 1 / (ser_time + Robot_time)

print("-" * 40)
print("Single Server with Infinite Capacity - (M/M/1): (∞/FIFO)")
print("-" * 40)
print(f"The mean arrival rate per second: {lam:.2f}")
print(f"The mean service rate per second: {mu:.2f}")


if lam < mu:
    Ls = lam / (mu - lam)
    Lq = Ls - (lam / mu)
    Ws = Ls / lam
    Wq = Lq / lam
    
    print(f"Average number of objects in the system: {Ls:.2f}")
    print(f"Average number of objects in the conveyor: {Lq:.2f}")
    print(f"Average waiting time of an object in the system: {Ws:.2f} secs")
    print(f"Average waiting time of an object in the conveyor: {Wq:.2f} secs")
    print(f"Probability that the system is busy: {lam / mu:.2f}")
    print(f"Probability that the system is empty: {1 - (lam / mu):.2f}")
else:
    print("Warning! Objects overflow will happen in the conveyor.")

print("-" * 40)
```

## Output :

<img width="688" alt="Screen Shot 1946-08-15 at 10 56 20" src="https://github.com/user-attachments/assets/8f5b36a0-4377-49a4-b29a-ee77e6dcf501">

## Result :
The average number of materials in the system and in the conveyor, as well as the waiting times, have been successfully calculated.
