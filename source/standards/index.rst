Standards
=========

In this part of the workshop, we will introduce relevant standards and formats that are used throughout the workshop.
As mentioned in :numref:`workshop_philosophy` we will cover a range of standards from various domains, and attempt to demonstrate how they can be linked together through the use of harmonised semantics (see, for example, :cite:t:`neal_harmonizing_2019`).

The hands-on tutorials will include specific options to help attendees gain familiarity with the standards, the tools for working with them, and the APIs and services that can be used to integrate them into your own tools and methods.

Coordinating standards development
----------------------------------

When discussing standards in the context of this workshop, we primarily refer to community-based, grass-roots, standardisation efforts. Different communities have different approaches to developing, maintaining, and promoting their standards. The Computational Modelling in Biology Network (COMBINE, https://co.mbine.org/) was established to coordinate the development of the various community standards and formats for computational models (see :cite:t:`waltemath_first_2020` for a summary of early efforts). Standards accepted as core standards within the COMBINE community are expected to meet a minimal set of requirements in the management of the supporting community.

COMBINE standards span several domains models and their use. This includes `CellML <https://cellml.org>`_, the `Systems Biology Markup Language (SBML) <https://sbml.org/>`_, and `NeuroML <https://neuroml.org/>`_ for describing various types of models; and the `Simulation Experiment Description Markup Language (SED-ML) <https://sed-ml.org/>`_ for the use of models in numerical simulation experiments. There are also standards for graphical representation of models and standards for synthetic biology.

.. admonition:: Exercise

    Explore the COMBINE website to discover the current set of core standards and all the related standards and projects. **Extra for experts:** volunteer to `help with the new COMBINE website <https://github.com/combine-org/combine-org.github.io/issues>`_!


Standards aid model reuse
-------------------------

While sharing a model implementation in any way is significantly better than not sharing at all, unless a model is shared in a standard format it rapidly becomes inaccessible as software disappears or becomes unusable, requirements can no longer be met, etc. Sharing a model in a standard format ensures that it continues to be accessible - for example, models encoded in CellML or SBML 20 years ago can still be interpreted by current software tools even though the current tools did not exist at all 20 years ago. :cite:t:`mendes_reproducibility_2023` presents an extremely enlightening experience of the process required to resurrect a 20 year old model.

Furthermore, the modularity inherent in these standards enables parts of models to be reused. While tools and methods for the automated discovery and reuse of models and parts of models continue to themselves become more accessible (for example, see :cite:`shahidi_hierarchical_2021` or :cite:`shahidi_sbml_2022`), model reuse is currently primarily a manual process.

.. admonition:: Exercise

    Explore the reproducibility portal https://reproducibilityportal.org/ and see if you can discover some part of a model that might be of interest to you. Grab the Antimony code for that reaction and paste it into `MakeSBML`_ to generate a new SBML model.

The above exercise makes use of the `Antimony <https://github.com/sys-bio/antimony>`_ :cite:`smith_antimony_2009` model definition language as a Human readable form of the models available on the `Reproducibility Portal`_. The :ref:`figure below <reproducibility_portal_antimony>` shows an example of the Antimony format. Parts of the model (for example the reaction rate rules) can be easily copy-and-pasted into the `MakeSBML`_ web-application to generate a new SBML model. Using MakeSBML to translate the Antimony text into SBML and then translate the SBML back into Antimony makes it easy to see what additional information is needed to make a complete model.

.. _reproducibility_portal_antimony:
.. figure:: ../_static/reproducibility-portal-antimony.png
   :width: 600
   :alt: Image showing the Antimony model language in the reproducibility portal.

   A portion of the `model <https://reproducibilityportal.org/model/647a4b1877b6669655060cd2>`_ definition in the Antimony format at the reproducibility portal.

The above exercise also demonstrates a collection of web applications that consist of relatively lightweight implementations sitting on top of well established infrastructure.

Reuse is further enhanced when models and supporting data and knowledge are shared in a manner the supports discovery and accessibility. The `SPARC Portal`_, for example, provides extensive metadata with all "datasets" to enable detailed exploration of the content of the repository.

.. admonition:: Exercise

    Head over to the `SPARC Portal`_ and see if you can find an `organ scaffold`_ for your favourite species. And then see if you can compare to other species.

Harmonised semantics to aid comprehension
-----------------------------------------

Using suitable standards to encode a model and related simulation experiments greatly improves the FAIRness of a model, leading to improved tools and methods to help potential users evaluate the credibility of a model they may want to reuse. Beyond the model itself, there is a lot of essential knowledge that needs to be shared alongside the model to enable someone (or some tool) to understand the model. Who created the model, why it was created, how parameters were determined, etc., are all important pieces of knowledge that help potential future uses of a model. This is particularly critical for any model or simulation being translated to clinical applications.

Semantic annotation provides a technical solution for how we can associate additional knowledge with out models. The freedom and wealth of the semantic web, however, provides a platform for everyone to do make their annotations in their own very niche manner. Harmonising our annotation approaches and aligning utilised terminologies allows a given community to ensure that crucial knowledge is represented in a manner that makes it Findable, Accessible, Interoperable, and Reusable throughout that community and potentially more broadly.

Within the SPARC community, for example, the annotation of anatomical entities is now well established with common terminologies being used across all aspects. Segmented image data, anatomical maps, image, cell location, and time series data can all have suitable anatomical locations defined in a manner that is interoperable across the wealth of tools and resources in SPARC. And then via work with the `Common Fund Data Ecosystem <https://commonfund.nih.gov/dataecosystem>`_ this knowledge is then accessible much more broadly than just SPARC.

.. admonition:: Exercise

    Head to the `SPARC Portal`_ and specifically take a look at the `anatomical connectivity flatmap`_. For each species' flatmap you are able to explore the relevant content of the repository via the dataset marker points that are displayed on the map. Similarly, the facets on the `data and model browser <https://sparc.science/data?type=dataset>`_ are only possible due to the extensive and harmonised annotation of the datasets.

While it is well established that comprehensive model annotation is an important goal to strive for, it can also be a very tedious task to perform. Doing model annotation correctly is, furthermore, a task that can require significant training. Tools that can automate annotation and ease the burden on model authors are therefore needed. One such tool is An Automated Model Annotation System (`AMAS`_, :cite:`shin_automated_2023`), which predicts and recommends annotations for systems biology models.

.. admonition:: Exercise

    Install `AMAS`_ following the instructions available in the `AMAS documentation <https://amas.readthedocs.io/en/latest/>`_ and then try to use the tools to find recommendations for species and reactions in the demonstration model. And also try updating the model based on those recommendations.

    The demonstration model used in the documentation is available from https://www.ebi.ac.uk/biomodels/BIOMD0000000190#Files, download the file :file:`BIOMD0000000190_url.xml` and rename it :file:`BIOMD0000000190.xml`.

.. warning::

    We recommend installing the AMAS package into a clean Python virtual environment to avoid contamination of your system Python and/or version conflicts with required dependencies.


Standardised packaging to improve sharing
-----------------------------------------

A modelling study or project will invariably consist of many different resources, and each resource may evolve independently over time. For example, data collected to use in a parameter estimation task is unlikely to change, whereas a simulation experiment description may go through many iterations as the best numerical algorithm is determined.

One solution that enables authors to package up the collection of resources needed to share a given study or project at a point in time is the Open Modelling EXchange format (OMEX) :cite:`bergmann_combine_2014`, also known as a '*COMBINE Archive*', illustrated in the :ref:`figure below <combine_archive_image>`. This format is a structured ZIP file that defines the content of the archive in a standardised manner, allowing different software tools and applications to import a given archive and extract whichever resources in the archive the tool is able to work with. For example, a model visualisation tool may work with the visual representation of the model, whereas a simulation tool would more likely work with a simulation description.

.. _combine_archive_image:
.. figure:: ../_static/OMEX-archive.png
   :width: 600
   :alt: Image showing an example COMBINE Archive file.

   A COMBINE Archive defines a structured ZIP file that enables modelling projects to be shared in a manner that aims to be complete and synchronised. Image from :cite:t:`bergmann_combine_2014`.

.. admonition:: Exercise

    The `Physiome`_ journal publishes articles which describe a reproducible model implementation associated with a peer-reviewed scientific article. Take a look at the currently published articles and see if you can find the OMEX archive file for a given article. Try downloading the archive, renaming it to a :file:`.zip` and extracting the archive. Then see if you can match up the contents of the archive to the description given in the article.

Another example of this approach of standardised packaging of a project or study into single object to aid sharing is the SPARC Dataset Structure (SDS) :cite:p:`bandrowski_sparc_2021`. While developed initially for experimental data collected, models created, and analyses performed across the `SPARC <SPARC Portal>`_, this is now being extended to include a wider range of data and knowledge. In particular, extensions to support clinical data are a large focus of the 12 Labours project.

.. admonition:: Exercise

    Lets explore a few different types of datasets on the SPARC Portal. For each of the following datasets, take a look around the dataset details pages - the :guilabel:`Files` view gives the most detailed view of the SPARC dataset structure; the :guilabel:`Gallery` provides a visual exploration interface that is built using the metadata provided in the SDS; and the specific viewers available via the gallery let you dive into the data.

    * https://sparc.science/datasets/54
    * https://sparc.science/datasets/32
    * https://sparc.science/datasets/157 (look for the additional action buttons in the top left panel)

.. _Reproducibility Portal: https://reproducibilityportal.org/
.. _MakeSBML: https://sys-bio.github.io/makesbml/
.. _SPARC Portal: https://sparc.science
.. _organ scaffold: https://docs.sparc.science/docs/organ-scaffolds
.. _anatomical connectivity flatmap: https://sparc.science/maps?type=ac
.. _AMAS: https://github.com/sys-bio/amas
.. _Physiome: https://journal.physiomeproject.org