Community & reuse
=================

In this part of the workshop, we will demonstrate how standards are used to share information across modelling tools.
We show how this could be reused in your own work using your own tools.

The following exercises assume some familiarity with CellML and OpenCOR. For those without any familiarity, please see :numref:`opencor_tutorial`.

.. admonition:: Exercise 1

    This exercise is about running the `Fabbri et al. 2017 model`_ of a human sinus node cell using two different tools: `OpenCOR`_ and the `SPARC Portal`_.
    First:

    - Install `OpenCOR`_;
    - Open the `CellML version`_ of the `Fabbri et al. 2017 model`_;
    - Switch to the ``Simulation`` mode;
    - In the ``Simulation`` panel, set the ``Ending point`` to ``3.0`` (seconds) and the ``Point interval`` to ``0.001`` (seconds);
    - In the ``Parameters`` panel, right click on the ``V`` parameter under the ``Membrane`` heading (component) and then click on the ``Plot Against Variable Of Integration`` menu item; and
    - Run the simulation.

    The trace should be the same as the one you get when running the `Fabbri et al. 2017 model`_ from the `SPARC Portal`_:

    - Open the `Simulation Viewer <https://sparc.science/datasets/simulationviewer?id=135>`__ for the `Fabbri et al. 2017 model`_ `dataset <https://sparc.science/datasets/135>`__; and
    - Click on the ``Run Simulation`` button.

.. admonition:: Exercise 2 - Reuse

    This exercise is about reusing the `Fabbri et al. 2017 model`_ and adding to it a model a neuron, and then simulating it using different spike frequencies, numbers, and amplitudes. First, starting from the above `CellML version`_ of the `Fabbri et al. 2017 model`_:

    - Implement the `ODE-based version <https://brian2.readthedocs.io/en/stable/user/converting_from_integrated_form.html>`_ of the `Gerstner & Kistler 2002 model <https://psycnet.apa.org/doi/10.1017/CBO9780511815706>`_ of a neuron; and
    - Connect it to the `Fabbri et al. 2017 model`_ through the ODE for the ``V`` variable in the ``Membrane`` component; and
    - Run the combined model and experiment by changing the spike frequency, the spike number, and the spike amplitude of the neuron part of your combined model.

    The trace should be the same as the one you get when running the Fabbri-based composite model from the `SPARC Portal <https://sparc.science/>`_:

    - Open the `Simulation Viewer <https://sparc.science/datasets/simulationviewer?id=157>`__ for the Fabbri-based composite model `dataset <https://sparc.science/datasets/157>`__;
    - Change the ``Spike frequency``, the ``Spike number``, and the ``Spike amplitude`` values as needed; and
    - Click on the ``Run Simulation`` button.

As discussed and demonstrated in :numref:`scaffold_mapping_tools`, the `SPARC scaffold mapping tools`_ provide a collection of pre-defined `organ scaffold`_ geometries. As the scaffold mapping tools are built on top of a generic workflow application, those same tools can be configured to use the organ scaffolds in other ways. A particularly common use-case is the exporting of an organ scaffold into various formats for use in other tools. If you have been through the exercise in :numref:`scaffold_mapping_tools` you will be familiar with exporting organ scaffolds as WebGL suitable for use on the `SPARC Portal`_. In the following exercise we look at exporting organ scaffolds to `STL`_ and `VTK`_ formats.

.. admonition:: Exercise

    If you have not installed the `SPARC scaffold mapping tools`_, please follow the instructions available via that page to install the application.

    After launching the mapping tools application, we first will need to create a suitable workflow for creating an organ scaffold and exporting it to the chosen format. The steps required in such a workflow are

    * :guilabel:`Scaffold Creator`, to define the organ scaffold;
    * :guilabel:`Argon Viewer`, to define the graphics scene to be exported; and
    * :guilabel:`Argon Scene Exporter`, to perform the export.

    These steps should be arranged and connected as shown below.

    .. image:: ../_static/scaffold-exporter-workflow.png
        :width: 600

    The only step requiring configuration is the :guilabel:`Argon Scene Exporter` step, which can be configured to define the desired export type (i.e., STL or VTK) and the directory in which to save the exported files.

    Once configured and saved, the workflow can be executed. The first interactive step is to define the organ scaffold to be exported. Once defined, the next step is to configure the scene to be exported. Once the scene is configured, selected :guilabel:`Done` will proceed to the execute the export step and the workflow will be complete.

    The exporter step can now be reconfigured to export to a different format and the workflow executed again to produce that export.

    Scaffolds exported to the VTK format can be tested using the freely available `Glance <https://kitware.github.io/glance/app/>`_ web-app. An example of the pig heart scaffold exported to VTK and rendered in Glance is shown below.

    .. image:: ../_static/pig-heart-vtk.png
        :width: 600

    Similarly, exported STL models can be tested using the freely available `ViewSTL <https://www.viewstl.com/>`_ web-app. The pig heart scaffold exported to STL is shown below.

    .. image:: ../_static/pig-heart-stl.png
        :width: 600



.. _CellML version: https://models.physiomeproject.org/workspace/486/rawfile/55879cbc485e2d4c41f3dc6d60424b849f94c4ee/HumanSAN_Fabbri_Fantini_Wilders_Severi_2017.cellml
.. _Fabbri et al. 2017 model: https://dx.doi.org/10.1113/jp273259
.. _OpenCOR: https://opencor.ws/
.. _SPARC Portal: https://sparc.science/
.. _SPARC scaffold mapping tools: https://sparc.science/resources/1mv8q3JckdpSYpPK9dvdKx
.. _organ scaffold: https://docs.sparc.science/docs/organ-scaffolds
.. _STL: https://en.wikipedia.org/wiki/STL_(file_format)
.. _VTK: https://vtk.org/
.. _scaffold creator: https://abi-mapping-tools.readthedocs.io/en/v1.2.1/mapclientplugins.scaffoldcreator/docs/index.html
