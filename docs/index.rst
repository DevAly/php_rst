.. highlight:: php

Synopsis
========

Find the position of the first occurrence of a substring in a string

.. py:function:: int strpos(string $heystack, mixed $needle, [, mixed $offset=0])

Or

.. function:: strpos(string haystack, mixed value, [, integer offset=0])

   :param haystack: String being searched
   :param needle: String being searched for
   :param offset: Search offset from beginning of string
   :type haystack: string
   :type value: mixed
   :type offset: integer
   :rtype: Position of needle

Description
===========

Find the numeric position of the first occurrence of ``$needle`` in the ``$haystack`` string.


Parameters
==========

``$haystack``
    The string to search in.
``$needle``
    If ``$needle`` is not a string, it is converted to an integer and applied as the ordinal value of a character.
``$offset``
    If specified, search will start this number of characters counted from the beginning of the string. Unlike `<strrpos>`_ and `<strripos>`_, the offset cannot be negative.


Return values
=============

Returns the position of where the needle exists relative to the beginning of the ``$haystack`` string (independent of offset). Also note that string positions start at 0, and not 1.
Returns FALSE_ if the needle was not found.

.. warning:: This function may return Boolean FALSE_, but may also return a non-Boolean value which evaluates to FALSE_. Please read the section on `Booleans`__ for more information. Use `the === operator`__ for testing the return value of this function.

__ language.types.boolean
__ language.operators.comparison

Changelog
=========

================  ============================================================
Version           Description
================  ============================================================
5.2.6             Something cool happened
5.2.2             If the `$offset` parameter indicates the position of a negative truncation or beyond, false is returned. Other versions get the string from start.
================  ============================================================

Examples
========

Using ===
---------
Code::

    <?php
    $mystring = 'abc';
    $findme   = 'a';
    $pos = strpos($mystring, $findme);

    // Note our use of ===.  Simply == would not work as expected
    // because the position of 'a' was the 0th (first) character.
    if ($pos === false) {
        echo "The string '$findme' was not found in the string '$mystring'";
    } else {
        echo "The string '$findme' was found in the string '$mystring'";
        echo " and exists at position $pos";
    }
    ?>


Using !==
---------
Code::

    <?php
    $mystring = 'abc';
    $findme   = 'a';
    $pos = strpos($mystring, $findme);

    // The !== operator can also be used.  Using != would not work as expected
    // because the position of 'a' is 0. The statement (0 != false) evaluates
    // to false.
    if ($pos !== false) {
        echo "The string '$findme' was found in the string '$mystring'";
        echo " and exists at position $pos";
    } else {
        echo "The string '$findme' was not found in the string '$mystring'";
    }
    ?>

Using an offset
---------------
Code::

    <?php
    // We can search for the character, ignoring anything before the offset
    $newstring = 'abcdef abcdef';
    $pos = strpos($newstring, 'a', 1); // $pos = 7, not 0
    ?>


Notes
=====

.. note:: This function is binary-safe.


See also
=========
- `<stripos>`_
- `<strrpos>`_
- `<strripos>`_
- `<strstr>`_
- `<strpbrk>`_
- `<substr>`_
- `<preg_match>`_

.. _FALSE: false