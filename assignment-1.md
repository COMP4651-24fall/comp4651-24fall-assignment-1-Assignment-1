# COMP4651 Assignment 01: EC2 Measurement (8 marks)

### Deadline: 23:59, Oct. 10, Thursday

---

### Name: 
### Student Id:

### Email:

---



## Question 1: Measure the EC2 CPU and Memory performance

1. (0.5 mark) Report the name of measurement tool used in your measurements (you are free to choose *any* open source measurement software as long as it can measure CPU and memory performance). Please describe your configuration of the measurement tool, and explain why you set such a value for each parameter. Explain what the values obtained from measurement results represent (e.g., the value of your measurement result can be the execution time for a scientific computing task, a score given by the measurement tools or something else).

    > Your answer goes here.

2. (1 mark) Run your measurement tool on general purpose `t2.small`, `t3.medium`, and `c3.large` Linux instances, respectively, and find the performance differences among these instances. Launch all the instances in the **N. Virginia** region. Does the performance of EC2 instances increase commensurate with the increase of the number of vCPUs and memory resource?

    In order to answer this question, you need to complete the following table by filling out blanks with the measurement results corresponding to each instance type.

    | Size        | CPU performance | Memory performance |
    | ----------- | --------------- | ------------------ |
    | `t2.small`  |                 |                    |
    | `t3.medium` |                 |                    |
    | `c3.large`  |                 |                    |

    > Region: `N. Virginia`. Use `Ubuntu Server 20.04 LTS (HVM)` as AMI.

## Question 2: Measure the EC2 Network performance

1. (2 mark) The metrics of network performance include **TCP bandwidth** and **round-trip time (RTT)**. Within the same region, what network performance is experienced between instances of the same type and different types? In order to answer this question, you need to complete the following table.

    | Type                      | TCP b/w (Mbps) | RTT (ms) |
    | ------------------------- | -------------- | -------- |
    | `t2.small` - ``t2.small`` |                |          |
    | `t3.medium` - `t3.medium` |                |          |
    | `c3.large` - `c3.large`   |                |          |
    | `t2.small` - `c3.large`   |                |          |
    | `t3.medium` - `c3.large`  |                |          |
    | `t3.medium` - `t2.small`  |                |          |

    > Region: `N. Virginia`. Use `Ubuntu Server 20.04 LTS (HVM)` as AMI. You should launch **6** instances in total.

2. (1 mark) What about the network performance for instances deployed in different regions? In order to answer this question, you need to complete the following table.

    | Connection                | TCP b/w (Mbps) | RTT (ms) |
    | ------------------------- | -------------- | -------- |
    | N. Virginia - Oregon      |                |          |
    | N. Virginia - N. Virginia |                |          |
    | Oregon - Oregon           |                |          |

    > Region: `N. Virginia`/`Oregon`. Use `Ubuntu Server 20.04 LTS (HVM)` as AMI. All instances are `t3.medium`.
    
3. (1 mark) Is network performance consistent over time? You can do measurements at different times of a day and compare the results. Please give at least 2 possible reasons why network performance is inconsistent.

    > Your answer goes here.


## Question 3：Decision Trees

We would like to construct a decision tree for n vectors each with m attributes.

1. (0.5 mark) Assume that there exists i and j such that for ALL vectors $X$ in our training data, these attributes are equal ($x_i=x_j$ for all vectors where xi is the i’th entry in the vector $X$). Assume that we break ties between them by using $x_i$ (that is, if both lead to the same conditional entropy we would use $x_i$). Can removing attribute $j$ from our training data change the decision tree we learn for this dataset? Explain briefly.


2. (0.5 mark) Assume we have two equal vectors $X$ and $Z$ in our training set (that is, all attributes of $X$ and $Z$ including the labels are exactly the same). Can removing $Z$ from our training data change the decision tree we learn for this dataset? Explain briefly.



For the next set of questions consider a dataset with continuous attributes. For such attributes we can use threshold splits to determine the best partition for a set of vectors. Assume we are at the root and we have n vectors, all with different (continuous) values for attribute $x_1$.

3. (0.5 mark) Assume we would like to use binary splits. For such splits we need to choose a value a and split the data by propagating all vectors with $x_1<a$ to the left and those with $x_1>=a$ to the right. For any value of $a$ we consider we would like to have at least one vector assigned to each of the two branches of the split. How many values of a do we need to consider?

4. (0.5 mark) Assume we would like to use three way splits. For such splits we need to chose values $a$ and $b$ such that $a$ < $b$ and split the data into three sets: $x_1 < a, a <= x_1 < b,
x_1 >= b$. Again we require that for any value of $a$ and $b$ that we consider at least one vector would be assigned to each of the three branches. How many $\{a,b\}$ do we need to consider?

5. (0.5 mark) For a given three way split at the root (parameterized by an $\{a,b\}$ pair) can we reconstruct the same split with a tree that uses only binary splits?
If no briefly explain why.
If yes, show the tree that leads to the same set of leaves with the same nodes in each leaf as the three way split.