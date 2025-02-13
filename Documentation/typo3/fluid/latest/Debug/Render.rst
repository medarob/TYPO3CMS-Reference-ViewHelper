.. include:: /Includes.rst.txt

.. _typo3-fluid-debug-render:

============
debug.render
============


Debuggable version of :ref:`f:render <typo3-fluid-render>` - performs the
same rendering operation but wraps the output with HTML that can be
inspected with the admin panel in frontend.

Replaces ``f:render`` when the admin panel decides (see
:php:`ViewHelperResolver` class). Also possible to use explicitly by using
``f:debug.render`` instead of the normal ``f:render`` statement.

Arguments
=========


.. _debug.render_debug:

debug
-----

:aspect:`DataType`
   boolean

:aspect:`Default`
   true

:aspect:`Required`
   false
:aspect:`Description`
   If true, the admin panel shows debug information if activated,

.. _debug.render_section:

section
-------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Section to render - combine with partial to render section in partial

.. _debug.render_partial:

partial
-------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Partial to render, with or without section

.. _debug.render_arguments:

arguments
---------

:aspect:`DataType`
   mixed

:aspect:`Default`
   array ()

:aspect:`Required`
   false
:aspect:`Description`
   Array of variables to be transferred. Use {_all} for all variables

.. _debug.render_optional:

optional
--------

:aspect:`DataType`
   boolean

:aspect:`Required`
   false
:aspect:`Description`
   If TRUE, considers the *section* optional. Partial never is.

.. _debug.render_default:

default
-------

:aspect:`DataType`
   mixed

:aspect:`Required`
   false
:aspect:`Description`
   Value (usually string) to be displayed if the section or partial does not exist

.. _debug.render_contentas:

contentAs
---------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   If used, renders the child content and adds it as a template variable with this name for use in the partial/section
