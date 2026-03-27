.. You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Scripture Burrito for Wycliffe Associates
=========================================

.. image:: ../logo/burrito_logo.png

This fork documents the Wycliffe Associates usage profile for Scripture Burrito. The upstream model remains the foundation, but the schema and docs in this repository narrow several choices so WACS tools stay consistent.

Out of the box Scripture Burrito is designed to support the following types of data:

- :ref:`scripture_text_flavor`
- :ref:`scripture_audio_flavor` (beta)
- :ref:`scripture_sign_language_flavor` (beta)
- :ref:`scriptural_text_stories_flavor` (beta)

As interoperability is our primary goal, we are happy to accept proposals for new flavors based on common interchange scenarios. We have provided instructions and examples for :ref:`extending_scripture_burrito` by testing and implementing new flavors (using ``x-`` flavors). When multiple implementations can be demonstrated, we will consider adding them as official flavors in new schema releases.

If you learn best by example, see the `minimal flavor examples <https://github.com/bible-technology/sb_minimalFlavorExamples>`_.

This work has been a multi-year collaboration between several organizations, including `American Bible Society <https://americanbible.org/>`_, `Clear.Bible <https://www.clear.bible/>`_, `Eldarion <https://eldarion.com/>`_, `Bridge Connectivity Solutions <https://bridgeconn.com/>`_, `SIL <https://www.sil.org/>`_, `unfoldingWord <https://www.unfoldingword.org/>`_, `United Bible Societies <https://unitedbiblesocieties.org/>`_, and the work has been sponsored by `illumiNations <https://illuminations.bible/>`_.

Future Development
==================

See future development `milestones here <https://github.com/bible-technology/scripture-burrito/milestones>`_. The Scripture Burrito :ref:`committee` invites comments on all aspects of the schema and documentation. Please use `Github Issues <https://github.com/bible-technology/scripture-burrito/issues>`_ or `Github Discussions <https://github.com/bible-technology/scripture-burrito/discussions>`_ to provide feedback.


Documentation
=============

.. toctree::
   :maxdepth: 4

   introduction/index
   schema_docs/index
   flavors/index
   examples/index
   glossary
