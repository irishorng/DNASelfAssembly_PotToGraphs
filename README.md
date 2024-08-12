# DNASelfAssembly_PotToGraphs

### Mitchell VonEschen, Iris Horng, Holly Luebsen, Grace Bielefeldt

-----------------------------------------------------------

Full paper link: *coming soon*


We designed an algorithm with the intention of taking a pot as its input and outputting at least one valid graph that can be realized by that pot.

Inputs:
- A pot in the form of a string (ex. $` \{ \{a,\hat{b}\}, \{a,b \}, \{ \hat{a}^2, \hat{b} \}, \{ \hat{a}^2, b \} \}`$ would be written as '$`a,-b;a,b;-a2,-b;-a2,b`$') with hatted letters preceded by a negative, and exponents (if applicable) listed after each letter that is being exponentiated
- A desired order for a target graph, which can be preceded with a negative to indicate production of graphs of only that order (or next smallest if order entered is not applicable), or $`0`$ if the user wants the program to calculate and use the minimum possible order of all valid, realizable graphs
- A number of parameters that may affect graph generation:
  - `avoid_loops` Whether to avoid generating graphs with loops
  - `avoid_multiple_edges` Whether to avoid generating graphs with multi-edges
  - `ordering_to_use` How to prioritize the sequence in which tiles are ordered and then connected to each other
  - `specific_order` Whether to only display graphs of a particular, inputted order (as a negative value)
  - `choose_tile_ratios` Whether the user wants to specify the proportions of each tile in the pot to use in graph generation, and only display graphs that use that proportion
 
Output:
- All non-isomorphic graphs that can be made



# Overivew:

## Part 0 (User Input)
There are a variety of arguments that the user can choose:
- `pot_str` is a string representing the Pot that the user would like to use. It should be formatted using semicolons to separate each tile and commas to separate half-edge types within a tile. Use a number following each half-edge type to indicate its exponent. Use a negative sign prior to the half-edge type to indicate that it is a hatted half-edge.
- `order` is a number representing the order of the graph that the user would like to generate. Input `0` for the algorithm to automatically generate graphs of the minimum order. Input `-n` if the user only wants graphs of order `n`, where `n` is a natural number. Input any number greater than the minimal order if the user wants all graphs up to that order to be generated. If the given order is too small, the algorithm will default to the minimal order
- `choose_tile_ratios` is a boolean representing if the user wants to specify ratios to be used to generate graphs. If `TRUE`, user will be prompted once ratios have been generated
- `non_iso_graphs` is a boolean reprsenting if the user wants to generate all non-isomorphic graphs only. If `TRUE`, the algorithm will output all non-isomorphic graphs only.
- `avoid_loops` is a boolean representing if the user wants to avoid loops. If `TRUE`, loops may still be possible but are not prioritized
- `avoid_multiple_edges` is a boolean representing if the user wants to avoid multiple edges. If `TRUE`, multiple edges may still be possible but are not prioritized
- `max_graphs` is a number representing the maximum number of graphs that the algorithm should output. This serves as a caution so that the computer does not overload if there are too many possible graphs that can be made.

## Part 1 (Matrix Construction)
- `convert_pot(pot_str)` is a function that converts the inputted `pot_str` (string that represents the pot) into a vector pot (see paper for definition of vector pot)
  - input: `pot_str` pot written as a string
  - output: the pot_matrix and pot_vector as  `M` and `tiles` respectively

## Part 2 (Pot Evaluation)
- `check_max_order(M)` is a function that finds the minimum order of a graph that can be made from `M` (the pot matrix)
  - input: `M` the pot matrix outputted from the `convert_pot` function
  - output: `order` the minimum order of the graph as an integer 
- `pot_ratios(M, order)` is a function that finds the ratios of each tile that should be used to generate a graph. If the user had indicated `choose_tile_ratios = TRUE` in Part 0, then this function will use those ratios and ensure that those tile ratios generate a valid graph
  - input: `M` is the pot matrix, `order` is the order outputted from the `check_max_order` function
  - output: `ratios` a list of integers indicating the ratios of each tile that generate a graph
 
## Part 3 (Graph construction) 
This part involves the tile orderings and connecting tiles strategies
- `compound_ordering_with_values(ordering_1, ordering_1_values, ordering_2_values)` is a function that returns an ordering where the first ordering is further sorted by a second list of values
  - input:
  - output:
- 
  - 

## Part 4 (Non-Isomorphic Graphs)
This part involves checking for non-isomorphic graphs if the user indicated `non_iso_graphs = TRUE`
`generateAllNonIsoCanonical(list_of_dict)` is the general function that involves the following:
- `allPermutationsForBondEdge(BDict, bEdgeIndex)` is a function that


## Part 5 (Graph Visualization)
This part involves the visualization techniques used to print a digital visually appealing graph

