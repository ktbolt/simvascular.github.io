##Creating the geometry for the fluid domain

For most cardiovascular modeling applications, the geometry of the fluid domain is generated by segmenting blood vessels out of medical image data. This process is described on the main SimVascular documentation: http://simvascular.github.io/docsModelGuide.html. We now want delete all the caps off the model. Once you have done that, export it by right-clicking the model from the left-hand menu and selecting ``Export as Solid Model''. When SimVascular prompts you for a name and location for the exported model, make sure to add an .stl extension to make sure the exported model is in .stl format. We will perform the next step in Meshmixer, and Meshmixer only takes in .stl format surfaces.

<figure>
  <img class="svImg svImgMd" src="documentation/svFSI/fsi_tutorial/imgs/SV_Export_as_stl1.png">
  <figcaption class="svCaption" >Exporting the fluid geometry from SimVascular as an .stl for Meshmixer.</figcaption>
</figure>
