
<h2> Appendix </h2> 

<!-- =================================================================== -->
<!-- ========================== VTK File Format ======================== -->
<!-- =================================================================== -->

<h3 id="appendix_vtk_file_format"> VTK File Format </h3> 
The <a href="https://docs.vtk.org/en/latest/"> Visualization Toolkit (VTK)</a> compressed XML file format
(see <a href="https://docs.vtk.org/en/latest/design_documents/VTKFileFormats.html"> VTK file formats</a>)
is used by svFSIplus to store
<br>
<ul style="list-style-type:disc;">
<li> Finite element mesh </i>
<li> Boundary condition data </i>
<li> Simulation results </i>
</ul>

The VTK XML files store geometry data (points, lines, polygons, polyhedra) as well user-defined arrays
containing integer and float data

<ul style="list-style-type:disc;">
<li> Integer arrays - used to associate values (e.g. node and element IDs) with geometric entities </i>
<li> Float arrays - used to initialize state varaibles and set values for certain types of boundary conditions </i>
</ul>

The VTK XML file formats used are
<ul style="list-style-type:disc;">
<li> <strong>VTU</strong> format - Unstructured grid data used to store problem domains, fiber directions, and initial values. Files use a <strong>.vtu</strong> file extension. </li> 
<li> <strong>VTP</strong> format - Polygonal data used to store boundary surfaces (faces) and data. Files use a <strong>.vtp</strong> file extension.</li> 
</ul> 
