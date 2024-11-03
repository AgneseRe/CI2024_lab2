# Travelling Salesman Problem &#128681;

Explore optimization techniques for solving the **TSP** problem, using both a fast but approximate algorithm and a slower, yet more accurate one.

## Description
This project addresses the *Travelling Salesman Problem* (TSP), using two different approaches: a *greedy approach* that, from time to time, moves to the nearest city and an *evolutionary algorithm* based on *mutation* and *cross-over* operators. The performance of the algorithms are evaluated in terms of cost and number of steps accross various instances. TSP instances can be found in the following Wolfram Notebook: https://www.wolframcloud.com/obj/giovanni.squillero/Published/Lab2-tsp.nb.

## Greedy Algorithm
The **greedy** algorithm starts from a city and iteratively jumps to the nearest unvisited one. This process continues until all cities are visited. It's relatively fast, but it only provides a solution that approximates the shortest route. In the table below, the results obtained using the greedy algorithm and the optimal ones are compared. All costs are reported in *km*. China optimal route cost must be computed. It is not available in the Wolfram Notebook cited above.
| Instance | No. cities | Greedy Route Cost | Optimal Route Cost | Difference |
| -------- | ---------- | ----------------- | ------------------ | ---------- |
| Vanuatu  | 8          | 1475.53           | 1345.54            | +129.99    |
| Italy    | 46         | 4436.03           | 4172.76            | +263.27    |
| Russia   | 167        | 42334.16          | 32722.50           | +9611.66   |
| US       | 340        | 48050.03          | 39016.62           | +9033.41   |
| China    | 746        |                   | to be computed     | to be computed |

## Evolutionary Algorithm
The **evolutionary** algorithm iteratively evolves a population of individuals over a predefined number of generations (`NUM_GENERATIONS`). Using parents selection, mutation, cross-over and elitism, the algorithm explore and exploit the solution space effectively, aiming to find the optimal or a near-optimal solution to the TSP problem.

**Process**
- **Generating initial population**: initialize a population of `POPULATION_SIZE` random individuals. Each individual is constructed by randomly permuting (shuffling) the order of cities. Each individual represents a unique route of the cities;
- **Elite Preservation**: a small percentage (5%) of the best individuals, who form an *elite*, are preserved to ensure that the best qualities are carried forward to the next generation. They are transferred directly into the new generation, without mutation;
- **Creating new population**: a new offspring is constructed until the new population reaches the desidered size. Cross-over occurs between two selected parents to produce an offspring with a certain probability (`CROSSOVER_PROBABILITY`). A `MUTATION_PROBABILITY` % mutation operation is applied to the offspring. If crossover does not occur, the algorithm checks for mutation on a single parent instead.

## Graphic Route Visualization

## Contact
For questions, contact me at agnesere43@gmail.com.