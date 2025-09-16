## Introduction
Navcloud is used to define the area where drones can move, and to provide them wiht environment data they need to navigate around.
## Set Navcloud Boundaries
Before you  generate a navcloud it's recommended to set it's boundaries to avoid creating larger volumes than needed. This is especially important if you make a large level where only part of the area is actually playable. To set the navcloud boundaries you need to first add the 'Nav Cloud Boundaries' component to a new empty gameobject in the scene. When that object is selected, it will display a yellow cube widget in your scene for adjusting the navigation volume's placement and dimensions. The red volume displays the actual navigation volume that will be generated.
## Navcloud Generation
Navcloud can be generated from the Levelkit Tool.
If you don't have a Navcloud Boundaries set up in your scene, generating navcloud will generate it for the whole scene volume (which can take a long time for a large level).