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

    Explore the reproducibility portal https://reproducibilityportal.org/ and see if you can discover some part of a model that might be of interest to you. Grab the Antimony code for that reaction and paste it into MakeSBML to generate a new SBML model.