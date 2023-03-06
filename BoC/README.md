# Bill of Components for Magicdraw / Catia NoMagic

This model includes a customisation and scripts of for creating Bill of Components / Bill of Materials respecting inheritance and multiplicities. 


![model](https://github.com/amdx/magicdraw/blob/main/BoC/assets/bocTestmodel.png)

The objective at hand is to obtain a precise count of the types used to type part properties in the structure decomposition of a SOI (System of Interest). This task requires careful consideration of various factors such as inheritance, redefinition, and upper bounds of multiplicities. It is important to note that unbound multiplicities are not respected, and we believe that they do not exist.

To begin with, the scope of the generic table must be taken into account as it defines the starting point of the decomposition. This allows for the table to be easily copied and maintained by changing just one parameter. Additionally, inheritance and redefinition must be respected in order to obtain an accurate count of the types used.

Furthermore, the upper bound of the multiplicities must be considered while counting the types used. This ensures that the count accurately reflects the types used in the structure decomposition while taking into account the constraints imposed by the multiplicities.
By respecting these constraints, an accurate count can be obtained which can then be used to inform further analysis and decision-making, e.g. by filtering per classifier, stereotype or tagged value.

## Usage

### Getting started

To use BoC generic table, follow these steps:

1.  Copy the BoC generic table.
2.  Add a block to the table's scope. This block will be structurally decomposed, and all typed parts will be counted along the decomposition.

![Generic Table](https://github.com/amdx/magicdraw/blob/main/BoC/assets/genericTable.png)

### General Setup

To set up the table, follow these steps:

1.  Use the generic table "query" to define a decomposee, i.e. the block in the table's scope. This query forms a unique set of used types in the structure decomposition of the decomposee. The rows of the table contain precisely these types.
2.  In a custom a  script is executed, that takes the table's scope and the contextual element (i.e., This = the row, which represents one of the used types) as arguments. The script aggregates the structural decomposition of "this" per row.
3. Filter the Table accoringly to get a condensed list.  

Caveats:

-   The script is not optimized for huge models since it's executed per row.
-   Self-contained types create infinite recursion. The script has a blacklist of types to exclude from the aggregation to avoid those recursions. By default, "Pattern" is excluded.