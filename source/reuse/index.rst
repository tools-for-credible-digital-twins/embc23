Community & reuse
==============================

In this part of the workshop, we will demonstrate how standards are used to share information across modelling tools that can be utilised in clinical applications.
We will then show how this can be reused in people's own work using their own tools but now with credibility.

We will demonstrate how to create a FAIR physiological model that can be submitted to the Physiome journal to create an artifact to provide evidence of credibility.

.. admonition:: Exercise 1

    This exercise is about running the `Fabbri et al. 2017 model`_ of a human sinus node cell using two different tools: `OpenCOR`_ and the `SPARC Portal`_.
    First:

    - Install `OpenCOR`_;
    - Open the `CellML version`_ of the `Fabbri et al. 2017 model`_;
    - Switch to the ``Simulation`` mode;
    - In the ``Simulation`` panel, set the ``Ending point`` to ``3.0`` (seconds) and the ``Point interval`` to ``0.001`` (seconds);
    - In the ``Parameters`` panel, right click on the ``V`` parameter under the ``Membrane`` heading (component) and then click on the ``Plot Against Variable Of Integration`` menu item; and
    - Run the simulation.

    The trace should be the same as the one you get when running the `Fabbri et al. 2017 model`_ from the `SPARC Portal <https://sparc.science/>`_:

    - Open the `Simulation Viewer <https://sparc.science/datasets/simulationviewer?id=135>`_ for the `Fabbri et al. 2017 model`_ `dataset <https://sparc.science/datasets/135>`_; and
    - Click on the ``Run Simulation`` button.

.. admonition:: Exercise 2 - Reuse

    This exercise is about reusing the `Fabbri et al. 2017 model`_ and adding to it a model a neuron, and then simulating it using different spike frequencies, numbers, and amplitudes. First, starting from the above `CellML version`_ of the `Fabbri et al. 2017 model`_:

    - Implement the `ODE-based version <https://brian2.readthedocs.io/en/stable/user/converting_from_integrated_form.html>`_ of the `Gerstner & Kistler 2002 model <https://psycnet.apa.org/doi/10.1017/CBO9780511815706>`_ of a neuron; and
    - Connect it to the `Fabbri et al. 2017 model`_ through the ODE for the ``V`` variable in the ``Membrane`` component; and
    - Run the combined model and experiment by changing the spike frequency, the spike number, and the spike amplitude of the neuron part of your combined model.

    The trace should be the same as the one you get when running the Fabbri-based composite model from the `SPARC Portal <https://sparc.science/>`_:

    - Open the `Simulation Viewer <https://sparc.science/datasets/simulationviewer?id=157>`_ for the Fabbri-based composite model `dataset <https://sparc.science/datasets/157>`_;
    - Change the ``Spike frequency``, the ``Spike number``, and the ``Spike amplitude`` values as needed; and
    - Click on the ``Run Simulation`` button.

.. _CellML version: https://models.physiomeproject.org/workspace/486/rawfile/55879cbc485e2d4c41f3dc6d60424b849f94c4ee/HumanSAN_Fabbri_Fantini_Wilders_Severi_2017.cellml
.. _Fabbri et al. 2017 model: https://dx.doi.org/10.1113/jp273259
.. _OpenCOR: https://opencor.ws/
.. _SPARC Portal: https://sparc.science/
