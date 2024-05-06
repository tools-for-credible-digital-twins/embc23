Introduction
============

A number of currently funded projects have the ambition of developing virtual human models for clinical applications, both for populations (such as in virtual clinical trials) and for individuals - the so-called ‘Virtual Human Twin’, or VHT, which is often linked with continuously updated data from implantable and wearable devices.
Along with many others, we are particularly interested in the development of virtual human models that are based on multiscale biophysically-based models that incorporate physiological function from the molecular level to the organ and organ system level in order that they can interpret clinical measurements from genetic testing, blood biomarkers, clinical imaging and physiological function testing.
This is a huge undertaking that requires global collaboration and coordination.
The European `EDITH project <https://www.edith-csa.eu/>`_, the New Zealand `12 Labours project <https://tinyurl.com/12labours>`_, and the `SPARC portal <https://sparc.science>`_ are all contributing to this global effort.
The goal of this workshop is to showcase plans and progress towards developing software tools, computational models, devices, datasets, and clinical applications to support these initiatives.

In this `IEEE EMBC 2023 <https://embc.embs.org/2023/>`_ workshop, we will demonstrate a range of tools that encourage users to create, share, and publish physiological models in a reproducible and FAIR manner.
We will show how using appropriate standard formats and consistently adopting suitable practices eases the transition from reproducible model to reproducible publication, and begins to provide evidence of model credibility that is crucial for the translation of models into clinical applications.
We will demonstrate examples which are beginning to achieve such translation of models into clinical workflows designed to support specific clinical use-cases.

.. image:: ../_static/project-logos.png
   :width: 600
   :alt: Image showing the logos of the main projects associated with this workshop.

The workshop will use free and open-source software tools being developed for the `12 Labours project <https://tinyurl.com/12labours>`_, `SPARC <https://sparc.science>`_, and the `Center for Reproducible Biomedical Modeling <https://reproduciblebiomodels.org>`_.
We will provide hands-on tutorials using stand-alone desktop or web applications and using services or programming interfaces that could be more easily integrated into existing tooling and practices in your own lab.
Workshop facilitators will be on hand to help with installation and usage questions, and in-depth discussion regarding potential integration of the tools.
All tools and example models and data used in the workshop will be available via `this website <https://tools-for-credible-digital-twins.github.io/>`_ for attendees to access and share, along with suitable documentation to help attendees share what they have learnt with colleagues.

To help encourage the publication of reproducible and credible models, we have launched the `Physiome <https://journal.physiomeproject.org>`_ journal.
In this workshop, we will discuss recent developments with *Physiome* as we look to make the articles dynamic and interactive '*active papers*', demonstrating how the tools and practices covered throughout the workshop can lead to the publication of your work in this way.
Such *active papers* will provide building blocks for credible physiological modelling and translational science.

Credibility for us is defined as being able to have a clearly defined context for the model or simulation which uses contextually appropriate data.
Where verification, and validation is performed within this context.
We also specify the limitations of the model or simulation explicitly.
We use version control to track the model or simulation development history, and document the code as well as user and developer guides.
We also make sure that the model or simulation is FAIR, so third party users and developers can independently review the work.

Workshop outline
----------------

In the first half of the workshop, we will provide introductory presentations to ensure all attendees are given a common starting point from which to launch into the examples and tutorials.
We will present how the standards, tools, and practices documented in the following sections are being developed and applied in our own projects, with illustrative examples used to provide in-depth context.
Throughout the presentations we will endeavour to point to the specific tools being used and where the capability is available via API or service for integration into other tools.

In the second half, attendees will be encouraged to pick and choose from the range of guided tutorials that will be available in the following sections and work their way through the material on their own or in groups.
We will provide guidance on specific pathways through the tutorials that aim to address specific use-cases, and instructors will be on hand to advise and discuss.
The available instructors will include expert software developers and researchers.

For the hands-on part of the workshop, it would be useful for attendees to have access to their own laptop.
Workshop attendees will be provided information on software requirements, installers, etc. prior to the workshop (to help avoid potential connectivity issues on-site) and installers will be available during the workshop as needed.
A small number of instructor machines with all the software pre-installed will be available on-site as well.

.. _workshop_philosophy:

Workshop philosophy
-------------------

As you will see through out the hands-on tutorials, we will generally divide things into two distinct approaches.

One takes a more "systems biology" approach, generally used for the lumped-parameter or compartmental modelling and views the model (or collection of models) as the primary data.
In this part, the COMBINE Archive :cite:p:`bergmann_combine_2014` provides the container to house a piece of work and relevant standards are used to describe the models and simulation experiments typically used for these kinds of modelling projects.

The other approach is based more on taking experimental or clinical observations and measurements as the primary data, to which models or other computational analyses can be applied to or derived from.
In this part, we use the SPARC Dataset Structure (SDS) :cite:p:`bandrowski_sparc_2021` as the container of choice to house a piece of work, with similar standards used to describe the models and simulation experiments in addition to the rich metadata describing the experimental and/or clinical data.

We tend to make this distinction in approaches to provide clarity in selection of relevant tools to use to achieve a given task.
But throughout this workshop we will demonstrate how the use of common standards and harmonised semantic annotations enhance the interoperability between these approaches and ensure that relevant prior work can be reused regardless of how it was created.
This is particularly important as we look to evaluate credibility of modelling and simulation studies in the move to translate into clinical practice.

