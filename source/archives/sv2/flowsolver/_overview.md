## Overview

### Process Flow of SimVascular Simulation 

The following figure contains a schematic representation of the processes involved in running a simulation using SimVascular.

<figure>
  <img class="svImg svImgLg" src="archives/sv2/flowsolver/imgs/Fig_01.png">
  <figcaption class="svCaption" >Workflow for generating hemodynamic results of a cylindrical model starting from a stereolithography of its exterior surface</figcaption>
</figure>

We start off with the files coming from the [meshing](docsMeshing.html) of the analysis: these files contain nodal and connectivity information for the finite element mesh, located in the the _mesh-complete/mesh-surfaces/_ folder.

We then run **Presolver(svPre)** using the \*.svpre_ file. The \*.svpre file contains the set of instructions that define the boundary conditions, initial conditions, and geometrical configuration of our problem. The output of **svPre** is a set of files (**bct.dat, geombc.dat.1, restart.0.1, numstart.dat**) that are ready to be processed by **svSolver** to run a blood flow analysis. Running svSolver also need **solver.inp**, which provide further info for flowsolver.

Once the analysis is finished, the solver outputs files that characterize the finite element solution over a defined time period, typically several cardiac cycles. These files are taken by **svPost** to generate visualization files (typically *.vtu and *.vtp files) that are used to post-process and analyze the desired hemodynamic results. 

In the following sections the components of this flow chart will be discussed in detail.

### Units in Simulation

**svSolver**, just like many other Finite Element Programs, does not enforce a consistent set of physical units in the analysis, but it is up to the analyst to make sure that input data are dimensionally consistent.

To have a consistent set of units, users are advised to either work in CGS, MGS, or SI units; see the following table. 

<table class="table table-bordered">
<thead>
<tr>
  <th>Quantity</th>
  <th>CGS Unit</th>
  <th>MGS Unit</th>
  <th>SI Unit</th>
</tr>
</thead>
<tr>
  <td>Length</td>
  <td>cm</td>
  <td>mm</td>
  <td>m</td>
</tr>
<tr>
  <td>Mass</td>
  <td>gr</td>
  <td>gr</td>
  <td>Kg</td>
</tr>
<tr>
  <td>Time</td>
  <td>s</td>
  <td>s</td>
  <td>s</td>
</tr>
</table>

### Useful constants in Simulation

The following table gathers several important physical constants of blood given in different unit
systems.

<table class="table table-bordered">
<thead>
<tr>
  <th>Property</th>
  <th>CGS Unit</th>
  <th>MGS Unit</th>
  <th>SI Unit</th>
</tr>
</thead>
<tr>
  <td>Dynamic viscosity $\mu$ [M· L -1 · T -1 ]</td>
  <td>0.04 poise [gr· cm -1 · s -1 ]</td>
  <td>0.004 [gr· mm -1 · s -1 ]</td>
  <td>0.004 [Pa· s -1 ]</td>
</tr>
<tr>
  <td>Blood density $\rho$ [M· L -3 ]</td>
  <td>1.06 [gr· cm -3 ]</td>
  <td>0.00106 [gr· mm -3 ] </td>
  <td>1060 [Kg· m -3 ]</td>
</tr>
</table>

