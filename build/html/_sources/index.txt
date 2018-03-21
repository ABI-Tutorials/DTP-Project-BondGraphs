.. _dtp_cp_project_bondgraphs:

Project: Bond Graph
===================

Introduction
------------

The bond graph approach to formulating models dealing with mass and energy transfer was developed by Henry Paynter in the 1960s to represent electro-mechanical control systems :cite:`paynter1961analysis`. It was later extended to include chemical processes by :cite:`breedveld1984physical`, including concepts from the theory of network thermodynamics by Aharon Katchalsky and colleagues :cite:`oster1971network`. Papers by Peter Gawthrop and Edmund Crampin have brought the approach into the bioengineering domain :cite:`gawthrop2014energy,gawthrop2015hierarchical,gawthrop2015energetic,gawthrop2016modular`.

The first key idea, based on recognising that energy and power are the only quantities that are common across different physical systems, is to separate energy transmission from storage and dissipation, and to provide the concept of *potential* (called "effort" in the engineering literature) with units of Joules per some_quantity as the common driving force behind the *flow* of that some_quantity per second. The product of potential and flow is then always power in units of Joules per second. The "some_quantity" has units of metres, meters\ :sup:`3`\, coulombs, candela, moles or entropy for, respectively, rigid body mechanics, continuum mechanics (including fluid flow), electrical, electromagnetic, chemical and heat transfer processes. As explained further below, the second key concept is that of a *0-junction*, where potential is defined and mass balance is applied, and a *1-junction*, where flow is defined and energy balance is applied. The extraordinary utility of these concepts is to recognise that Kirchhoff's voltage law in electrical circuits, Newton's force balance in a mechanical system, and stoichiometric balance in a biochemical system, are all just different manifestations of the same underlying principle of energy conservation and can therefore be represented by the same bond graph equation.

Units
-----

Many physical systems can be described by a driving *potential* expressed as Joules per unit of some quantity, and a *flow* expressed as that quantity per second. The quantity could be coulomb, meters, moles, *etc.* in different physical systems. The power is always the product of the driving force and the flow expressed as Joules per second. The seven units of the SI system under the newly proposed definitions are now based on constants that are consistent with the use of Joules and seconds (together covering energy and power), metres, moles, entropy, coulombs and candela. Table~\ref{units} displays the bond graph concepts in the fluid mechanics domain.

+------------+--------------------------+--------------------------+----------------------------+------------------------------+--------------------------+---------------------------+
|            | Electrical Circuit       | Solid Mechanics          | Fluid Mechanics            | Biochemical Reaction         | HeatFlow                 | Electro-magnetics         |
+============+==========================+==========================+============================+==============================+==========================+===========================+
| Potential  | J.C :sup:`-1` (V)        | J.m :sup:`-1` (N)        | J.m :sup:`-3` (Pa)         | J.mol :sup:`-1` (G)          | J.e :sup:`-1` (K)        | J.cd :sup:`-1`            |
+------------+--------------------------+--------------------------+----------------------------+------------------------------+--------------------------+---------------------------+
| Quantity   | C                        | m                        | m :sup:`3`                 | mol                          | e                        | cd                        |
+------------+--------------------------+--------------------------+----------------------------+------------------------------+--------------------------+---------------------------+
| Flow       | C.s :sup:`-1`            | m.s :sup:`-1`            | m :sup:`3`.s :sup:`-1`     | mol.s :sup:`-1`              | e.s :sup:`-1`            | cd.s :sup:`-1`            |
+------------+--------------------------+--------------------------+----------------------------+------------------------------+--------------------------+---------------------------+
| Momentum   | J.s.C :sup:`-1`          | J.s.m :sup:`-1`          | J.s.m :sup:`-3`            | J.s.mol :sup:`-1`            | J.s.e :sup:`-1`          | J.s.cd :sup:`-1`          |
+------------+--------------------------+--------------------------+----------------------------+------------------------------+--------------------------+---------------------------+
| Compliance | C :sup:`2`.J :sup:`-1`   | m :sup:`2`.J :sup:`-1`   | m :sup:`6`.J :sup:`-1`     | mol :sup:`2`.J :sup:`-1`     | e :sup:`2`.J :sup:`-1`   | cd :sup:`2`.J :sup:`-1`   |
+------------+--------------------------+--------------------------+----------------------------+------------------------------+--------------------------+---------------------------+
| Resistance | J.s.C :sup:`-2`          | J.s.m :sup:`-2`          | J.s.m :sup:`-6`            | J.s.mol :sup:`-2`            | J.s.e :sup:`-2`          | J.s.cd :sup:`-2`          |
+------------+--------------------------+--------------------------+----------------------------+------------------------------+--------------------------+---------------------------+
| Inductance | J.s :sup:`2`.C :sup:`-2` | J.s :sup:`2`.m :sup:`-2` | J.s :sup:`2`.m :sup:`-6`   | J.s :sup:`2`.mol :sup:`-2`   | J.s :sup:`2`.e :sup:`-2` | J.s :sup:`2`.cd :sup:`-2` |
+------------+--------------------------+--------------------------+----------------------------+------------------------------+--------------------------+---------------------------+

Formulation
-----------

In bond graph formulation, there are four basic variables. These variables for different physical systems are listed in . In electrical engineering these variables are given by: potential :math:`\mu` is energy density or `voltage` (J.C :sup:`-1`), flow :math:`\upsilon` is `current` (C.s :sup:`-1`), time integral of potential :math:`p` is `momentum` (J.s.C :sup:`-1`) and time integral of flow :math:`q` is quantity or `coulombs` (C). Product :math:`\mu .\upsilon` is power (J.s :sup:`-1`) which is a generalised coordinate to model the complete systems residing in several energy domains. A bond with covariables :math:`\mu` and :math:`\upsilon` is therefore used to represent `transmission of energy`. The bond represents a mechanism for the transmission of energy and power, and the arrow head indicates the assumed direction of power flow (see :numref:`fig_dtp_cp_bondgraphproject_bond`). The flow :math:`\upsilon` and potential :math:`\mu` must satisfy conservation laws.

.. _fig_dtp_cp_bondgraphproject_bond:

.. figure:: _static/bond.png
   :align: center
   :width: 25%

   Representation of energy bond.

There are also the concept of `0-junction` and `1-junction` for conservation laws. The `0-junction` defines a common potential :math:`\mu` which ensures that the potential is identical at each port and imposes mass conservation constraint based on :math:`\upsilon`. The `1-junction` defines a common flow :math:`\upsilon` which ensures that the flow is identical at each port and imposes energy conservation constraint based on :math:`\mu`. Since sum of the flows is zero with :math:`\mu` constant for `0-junction` and sum of the potentials is zero with :math:`\upsilon` constant for `1-junction`, the transmission of power through junction is conserved for both kinds of junctions, that is:

.. math::

   \sum \mu. \upsilon=0

Bond graph elements
-------------------

Bond graph formulation is a graphical notation for the set of linear constraint equations (the conservation laws), but the constitutive relations (to be addressed next) can be nonlinear.

`Resistors`
~~~~~~~~~~~

Energy :math:`\mu` can be dissipated by a resistor `R` in proportion to the flow :math:`\upsilon` with an empirical relation which can be a simple linear relation such as Equation 2 or a complex nonlinear relation:

.. math::

   \mu=\upsilon R

`Storage elements`
~~~~~~~~~~~~~~~~~~

Energy :math:`\mu` can be stored statically by a capacitor `C` without any loss. In the bond graph terminology, a one-port capacitor relates energy to the quantity `q` or time integral of flow by an empirical relation such as Equation 4. The `C-element` stores `q` by accumulating the net flow :math:`\upsilon` to the storage element:

.. math::

   \mu=\dfrac{q}{C}

.. math::

   \dot q=\upsilon

`I-element`
~~~~~~~~~~~

Energy :math:`\mu` can be stored dynamically by an inductor `I` without any loss. In bond graph formulation, a one-port inductor relates flow to the momentum `p` or time integral of potential by an empirical relation such as Equation 7. The `I-element` stores `p` by accumulating the net potential :math:`\mu` to the storage element.

.. math::

   \upsilon=\dfrac{p}{I}

.. math::

   \dot p=\mu


:numref:`fig_dtp_cp_bondgraphproject_tetra` shows the relation of the state variables to the constitutive relations.

.. _fig_dtp_cp_bondgraphproject_tetra:

.. figure:: _static/tetrahedron.png
   :align: center
   :width: 25%

   State variables and constitutive relations in the bond graph approach.

Causality
~~~~~~~~~

Causality establishes the cause and the effect relationship. It specifically implies that either the potential or flow variable on that bond is known. Causality is generally indicated by a causal stroke at the end to which the potential receiver is connected. Elements which store or dissipate energy do not impose causality on the system, but they have preferred causality for computational reasons. These elements with their preferred causality are shown in :numref:`fig_dtp_cp_bondgraphproject_causality_element`.

.. _fig_dtp_cp_bondgraphproject_causality_element:

.. figure:: _static/causality_element.png
   :align: center
   :width: 25%

   Preferred causality for `R`, `C`, and `I` elements.

In the bond graph approach, junctions interconnect the corresponding elements and constrain the possible causalities of the element ports connected to it. A `0-junction` can only have one potential output. In a similar way, a `1-junction` can only have one flow output. :numref:`fig_dtp_cp_bondgraphproject_causality_jun` illustrates causality in four-port `0-junction` and `1-junction`.

.. _fig_dtp_cp_bondgraphproject_causality_jun:

.. figure:: _static/causality_jun.png
   :align: center
   :width: 50%

   Causality in four-port `0-junction` and `1-junction`.

The full Bond Graph muscle model is shown in :numref:`fig_dtp_cp_bondgraphproject_bondgraph`.

.. _fig_dtp_cp_bondgraphproject_bondgraph:

.. figure:: _static/bondgraph.png
    :align: center
    :width: 50%

    Full bond graph model.


This project was created as part of the Computational Physiology module in the `MedTech CoRE <http://medtech.org.nz>`_ Doctoral Training Programme.

This project requires you to put together what you have learned in the tutorials to define a complete workflow which will create the Hoisting device model using the Bond graph technique.

Procedure
---------

To generate a bond graph model starting from an ideal-physical model, a systematic method exist, which we will present here as a procedure. This procedure consists roughly of the identification of the domains and basic elements, the generation of the connection structure (called the junction structure), the placement of the elements, and possibly simplifying the graph. The procedure is different for the mechanical domain compared to the other domains. These differences are indicated between parenthesis. The reason is that elements need to be connected to difference variables or across variables. The potentials in the non-mechanical domains and the flows in the mechanical domains are the across variables we need.

Step 1 and 2 concern the identification of the domains and elements.

1. Determine which physical domains exist in the system and identify all basic elements like *C*, *I*, *R*, *SE*, *SF*, *TF* and *GY*. Give every element a unique name to distinguish them from each other.

2. Indicate in the ideal-physical model per domain a reference potential (reference flow with positive direction for the mechanical domains). Note that only the references in the mechanical domains have a direction.

Steps 3 through 6 describe the generation of the connection structure (called the junction structure).

3. Identify all other potentials (mechanical domains: flows) and give them unique names.

4. Draw these potentials (mechanical: flows), and not the references, graphically by `0-junctions` (mechanical: `1-junctions`). Keep if possible, the same layout as the IPM.

5. Identify all potential differences (mechanical: flow differences) needed to connect the ports of all elements enumerated in step 1 to the junction structure. Give these differences a unique name, preferably showing the difference nature. The difference between  :math:`\mu`:sub:`1` and :math:`\mu`:sub:`2` can be indicated by :math:`\mu` :sub:`12`.

6. Construct the potential differences using a `1-junction` (mechanical: flow differences with a `0-junction`) according to Figure 17, and draw them as such in the graph. The junction structure is now ready and the elements can be connected.

7. Connect the port of all elements found at step 1 with the `0-junctions` of the corresponding potential or potential differences (mechanical: `1-junctions` of the corresponding flows or flow differences).

8. Simplify the resulting graph by applying the following simplification rules (Figure 18):

   * A junction between two bonds can be left out, if the bonds have a ‘through’ power direction (one bond incoming, the other outgoing).

   * A bond between two the same junctions can be left out, and the junctions can join into one junction.

   * Two separately constructed identical potential or flow differences can join into one potential or flow difference.

We will illustrate these steps with a concrete example consisting of an  (Figure 19).


Project outline
---------------

In this project, we create a bond graph model of a hoisting device consisting of an electromotor fed by electric mains, a cable drum and a load (:numref:`fig_dtp_cp_bondgraphproject_schematic`).

.. _fig_dtp_cp_bondgraphproject_schematic:

.. figure:: _static/schematic.png
   :align: center
   :width: 50%

   Sketch of the hoisting device.

The mains is modelled as an ideal voltage source. At the electromotor, the inductance, electric resistance of the coils, bearing friction and rotary inertia are taken into account. The cable drum is the transformation from rotation to translation, which we consider as ideal. The load consists of a mass and the gravity force. Starting from the schematic in :numref:`fig_dtp_cp_bondgraphproject_model`, you would be able to construct a bond graph model using the steps mentioned above.

.. _fig_dtp_cp_bondgraphproject_model:

.. figure:: _static/model.png
   :align: center
   :width: 75%

   Possible ideal-physical model augmented with the domain information of step 1.

Additional info
---------------

* Voltage source is constant with given value of :math:`20` J.C\ :sup:`-1`.

* Load and rotary inertia are :math:`1` J.s\ :sup:`2` .m\ :sup:`-2` and :math:`2` J.s\ :sup:`2` .rad\ :sup:`-2`, respectively.

* Electric resistance is :math:`10000` J.s.C\ :sup:`-2` and bearing friction is :math:`10` J.s.rad\ :sup:`-2`.

Simulation
-------------------------------

Using the bond graph model, now we can derive the equations and implement them in OpenCOR. The equations that we are looking for are: conservation of flow for `0-junctions`, conservation of energy for `1-junctions`, and constitutive relations for the elements. The input boundary condition for solving this system of ODEs is the voltage source or *SE* in the bond graph model. By running the simulation, you would be able to plot the potential and flow for all the elements in time.


.. bibliography:: refs.bib
