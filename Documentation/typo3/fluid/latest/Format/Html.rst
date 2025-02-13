.. include:: /Includes.rst.txt

.. _typo3-fluid-format-html:

===========
format.html
===========


Renders a string by passing it to a TYPO3 `parseFunc`_.
You can either specify a path to the TypoScript setting or set the `parseFunc`_ options directly.
By default :ts:`lib.parseFunc_RTE` is used to parse the string.

Examples
========

Default parameters
------------------

::

   <f:format.html>###PROJECT### is a cool <b>CMS</b> (<a href="https://www.typo3.org">TYPO3</a>).</f:format.html>

Output::

   <p class="bodytext">TYPO3 is a cool <strong>CMS</strong> (<a href="https://www.typo3.org" target="_blank">TYPO3</a>).</p>

Depending on TYPO3 setup.

Custom parseFunc
----------------

::

   <f:format.html parseFuncTSPath="lib.parseFunc">###PROJECT### is a cool <b>CMS</b> (<a href="https://www.typo3.org">TYPO3</a>).</f:format.html>

Output::

   TYPO3 is a cool <strong>CMS</strong> (<a href="https://www.typo3.org" target="_blank">TYPO3</a>).

Data argument
--------------

If you work with TypoScript "field" property, you should add the current record as "data"
to the ViewHelper to allow processing the "field" and "dataWrap" properties correctly.

::

   <f:format.html data="{newsRecord}" parseFuncTSPath="lib.news">News title: </f:format.html>

After "dataWrap = |<strong>{FIELD:title}</strong>" you may have this Output::

   News title: <strong>TYPO3, greatest CMS ever</strong>

Current argument
-----------------

Use the current argument to set the current value of the content object.

::

   <f:format.html current="{strContent}" parseFuncTSPath="lib.info">I'm gone</f:format.html>

After "setContentToCurrent = 1" you may have this Output::

   Thanks Kasper for this great CMS

CurrentValueKey argument
-------------------------

Use the currentValueKey argument to define a value of data object as the current value.

::

   <f:format.html data="{contentRecord}" currentValueKey="header" parseFuncTSPath="lib.content">Content: </f:format.html>

After "dataWrap = |{CURRENT:1}" you may have this Output::

   Content: How to install TYPO3 in under 2 minutes ;-)

Inline notation
---------------

::

   {someText -> f:format.html(parseFuncTSPath: 'lib.parseFunc')}

Output::

   TYPO3 is a cool <strong>CMS</strong> (<a href="https://www.typo3.org" target="_blank">TYPO3</a>).

.. _parseFunc: https://docs.typo3.org/m/typo3/reference-typoscript/master/en-us/Functions/Parsefunc.html

Arguments
=========


.. _format.html_parsefunctspath:

parseFuncTSPath
---------------

:aspect:`DataType`
   string

:aspect:`Default`
   'lib.parseFunc_RTE'

:aspect:`Required`
   false
:aspect:`Description`
   Path to the TypoScript parseFunc setup.

.. _format.html_data:

data
----

:aspect:`DataType`
   mixed

:aspect:`Required`
   false
:aspect:`Description`
   Initialize the content object with this set of data. Either an array or object.

.. _format.html_current:

current
-------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Initialize the content object with this value for current property.

.. _format.html_currentvaluekey:

currentValueKey
---------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Define the value key, used to locate the current value for the content object

.. _format.html_table:

table
-----

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   The table name associated with the "data" argument.
