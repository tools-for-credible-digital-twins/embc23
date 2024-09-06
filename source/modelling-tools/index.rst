Modelling and Simulation Tools
==============================

Here we introduce several tools that we are developing in support of various projects, ranging from desktop applications through to web-based applications and programming interfaces.
As mentioned in :numref:`workshop_philosophy` we will cover a range of tools from various domains, and attempt to demonstrate how with the use of appropriate standards they can be chained together to achieve complex workflows through the use of harmonised semantics.

Using standards in your own tools
---------------------------------

One of the most important aspects of developing a standard is to ensure that the standard can be used by developers of the tools that should be supporting the standard. For example, modelling standards like `CellML`_, `SBML`_, and `SED-ML`_ have corresponding `libCellML`_, `libSBML`_, and `libSEDML`_ software libraries that provide the core infrastructure enabling tool developers to use the corresponding standard. Each of these libraries tends to actually be a collection of interconnected resources providing interfaces to different programming languages and/or paradigms.

A lot of effort nowadays goes into making sure these core tools are available for use on the web. For example, the tools mentioned in :numref:`section-standards` use a mixture of Python and Javascript to interact with them.

Some standards don't lend themselves well to having this kind of core software library or API for developers to directly use. For example, the SPARC dataset structure (SDS) discussed in :numref:`standard_packaging` is a very high-level specification of how to structure files in a dataset along with harmonised approaches for defining associated metadata. Nevertheless, given the well-defined specification tool developers are able to support the standard. `SODA`_ is a desktop application that helps guide users through the process of creating datasets that adhere to the SDS and then uploading them for publication on the `SPARC Portal`_.

Another tool that works with the SDS is `SPARC-me`_, a SPARC Metadata Editor. This tool aims to provide a Python-based API for working with datasets adhering to the SDS. SPARC-me can then be built into other tools and services to enable support for the SDS.

.. _opencor_tutorial:

Creating, editing, and simulating models with OpenCOR
-----------------------------------------------------

`OpenCOR`_ is an open-source cross-platform comprehensive modelling environment. OpenCOR has model creating, editing, and simulating capabilities, primarily using models encoded in the `CellML`_ format. Simulation experiments can be serialised using the `SED-ML`_ format as well as being able to import and export COMBINE Archive files (see :numref:`standard_packaging`).

The Physiome Model Repository (`PMR`_) is an extensive collection of models, primarily in the CellML format. PMR has comprehensive support for versioning model evolution over time (using the `Git <https://git-scm.com/>`_ distributed version control system), but we often find that this capability is poorly understood by our target users. To overcome this, OpenCOR directly integrates with PMR and guides the user through all aspects of using the version control system.

.. admonition:: Exercise

    The `OpenCOR tutorial`_ is an extensive trip through the capabilities of CellML, PMR, and OpenCOR. As the tutorial gradually builds upon lessons learnt in preceeding steps, it is useful to follow through the tutorial in its entirety. If time is pressing, however, some particular highlights worth jumping to are:

    * opening a model directly from PMR in OpenCOR [`link1 <https://tutorial-on-cellml-opencor-and-pmr.readthedocs.io/en/latest/open_existing.html>`_];
    * modularity and model reuse [`link2 <https://tutorial-on-cellml-opencor-and-pmr.readthedocs.io/en/latest/cellml_imports.html>`_];
    * generating procedural code from CellML models [`link3 <https://tutorial-on-cellml-opencor-and-pmr.readthedocs.io/en/latest/code_generation.html>`_]; and
    * depositing models into PMR using OpenCOR [`link4 <https://tutorial-on-cellml-opencor-and-pmr.readthedocs.io/en/latest/pmr_workspaces_in_opencor.html>`_].

.. _scaffold_mapping_tools:

Mapping data to organ scaffolds
-------------------------------

The `SPARC scaffold mapping tools`_ provide a suite of tools to enable data to registered to a common coordinate framework defined by an `organ scaffold`_. The scaffold mapping tools are actually a specialised release of the `MAP Client`_ workflow application, containing all the tools and resources required to achieve the scaffold mapping tasks.

.. admonition:: Exercise

    Install the `SPARC scaffold mapping tools`_ following the instructions available via that page. At this time, the current release of the scaffold mapping tools should be 0.21.4.

    Also available from the above link are three step-by-step tutorials demonstrating different mapping tasks. Namely embedding segmented data in a SPARC organ scaffold; mapping physiological data; and mapping image data from a flat preparation. Working through these tutorials will give a good sense of the capabilities that can be achieved due to the standards being used and the harmonisation of the metadata.


.. _libCellML: https://libcellml.org
.. _libSBML: https://sbml.org/software/libsbml/
.. _libSEDML: https://github.com/fbergmann/libSEDML
.. _CellML: https://cellml.org
.. _SED-ML: https://sed-ml.org
.. _SBML: https://sbml.org
.. _OpenCOR: https://opencor.ws
.. _OpenCOR tutorial: https://tutorial-on-cellml-opencor-and-pmr.readthedocs.io/
.. _libOpenCOR: https://opencor.ws/libopencor
.. _PMR: https://models.physiomeproject.org/
.. _SODA: https://docs.sodaforsparc.io/
.. _SPARC Portal: https://sparc.science
.. _SPARC-me: https://github.com/SPARC-FAIR-Codeathon/sparc-me
.. _SPARC scaffold mapping tools: https://sparc.science/resources/1mv8q3JckdpSYpPK9dvdKx
.. _organ scaffold: https://docs.sparc.science/docs/organ-scaffolds
.. _MAP Client: https://map-client.readthedocs.io/en/latest/
