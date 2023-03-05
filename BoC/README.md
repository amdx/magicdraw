# Bill of Components for Magicdraw / Natia NoMagic

This model includes a customisation and scripts of for creating Bill of Components / Bill of Materials respecting inheritance and multiplicities. 


![[bocTestmodel.png]]

The objective at hand is to obtain a precise count of the types used to type part properties in the structure decomposition of a SOI (System of Interest). This task requires careful consideration of various factors such as inheritance, redefinition, and upper bounds of multiplicities. It is important to note that unbound multiplicities are not respected, and we believe that they do not exist.

To begin with, the scope of the generic table must be taken into account as it defines the starting point of the decomposition. This allows for the table to be easily copied and maintained by changing just one parameter. Additionally, inheritance and redefinition must be respected in order to obtain an accurate count of the types used.

Furthermore, the upper bound of the multiplicities must be considered while counting the types used. This ensures that the count accurately reflects the types used in the structure decomposition while taking into account the constraints imposed by the multiplicities.
By respecting these constraints, an accurate count can be obtained which can then be used to inform further analysis and decision-making, e.g. by filtering per classifier, stereotype or tagged value.