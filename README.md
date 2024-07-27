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
