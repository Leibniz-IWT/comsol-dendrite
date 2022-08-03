# comsol-dendrite
This is a comsol implementation of a model for dendritic growth during the solidification of a pure metal. The model was developed in Comsol Multiphysics 5.6.

Author:
Nils Ellendt
University of Bremen
Particles & Process Engineering
ellendt@uni-bremen.de

A detailed description of the model equations can be found in:
Ferreira, Alexandre Furtado, Alexandre José da Silva, and José Adilson de Castro. "Simulation of the solidification of pure nickel via the phase-field method." Materials Research 9 (2006): 349-356.

https://www.researchgate.net/publication/250029636
http://dx.doi.org/10.1590/S1516-14392006000400002

An adaptive mesh was implemented in Comsol to allow local mesh refinement where needed (especially at the interface). 

The properties are grouped into phase field properties, material properties and nucleus properties:

![grafik](https://user-images.githubusercontent.com/70893730/182544686-c4af8648-fc70-4698-92da-b7d7c2b52b08.png)

Phase field arameters:

![grafik](https://user-images.githubusercontent.com/70893730/182544853-ac28b330-f071-4d03-91c8-f3c77dbe5dfc.png)

Material properties:

![grafik](https://user-images.githubusercontent.com/70893730/182544947-b9f01a92-c123-4317-9fac-1755acc14f18.png)

And nucleus properties:

![grafik](https://user-images.githubusercontent.com/70893730/182544996-866a64f9-cb8f-4421-96bc-8216e7d35ec3.png)

In "Component 1" you will find the acual phase field implementation:

![grafik](https://user-images.githubusercontent.com/70893730/182545105-a0bf54a3-fd8a-43cb-ae1f-0e3cb09ce4a1.png)

Variables are defined for the  interface angle theta, anisotropy functions for theta and epsilon and their derivative and square and the phase field functions g and h and their derivatives.

Random noise is applied to the growth to alloy some asymmetry effects to happen.

In the "Phae Field Pure Metal" entry, the PDEs are defined:

![grafik](https://user-images.githubusercontent.com/70893730/182545673-61365e18-49a7-48e7-9ec4-c48b18aed1cc.png)

in the form:

![grafik](https://user-images.githubusercontent.com/70893730/182545922-465f2dc3-4a50-4c62-9f05-afd827c655e5.png)

I am only showing the sections with entries:

![grafik](https://user-images.githubusercontent.com/70893730/182546015-9a57dc8e-547b-4014-826d-7bb5421db6e1.png)

![grafik](https://user-images.githubusercontent.com/70893730/182546063-3e02000e-b62c-4011-ae3b-0a1f29c038ee.png)

In this model, a zero flux condition is applied to all boundaries. You may want to use different boundary conditions for your case.

As an initial condition, a constant supercooled temperature is set to the whole domain with a nucleus (p=0) in the center with the radius given in the parameters.

![grafik](https://user-images.githubusercontent.com/70893730/182546489-2edbbdf6-dfca-49e3-a9e3-a6f26dc5a594.png)

The rest of the model is standard comsol settings. You can adjust the adaptive mesh settings in the solver:

![grafik](https://user-images.githubusercontent.com/70893730/182546849-2faa0a71-c0d1-4461-b49e-c5f6dd187a81.png)

I am sure that solver tuning is possible to speed up the calculation. This study was performed on a 12-core Intel Xeon machine with 256 GB RAM.


If you have questions about the model or if you want to contribute, please do not hesitate to send me an Email!
