SYNOPSIS
========

int function strpos( string :math:`haystack,     mixed `\ needle, int
$offset = 0 )

Find the position of the first occurrence of a substring in a string

DESCRIPTION
===========

Find the numeric position of the first occurence of ``$needle`` in the
``$haystack`` string

PARAMETERS
==========

-  ``$haystack`` The string to search in
-  ``$needle`` If ``$needle`` is not a string, it is converted to an
   integer and applied as the ordinal value of a character.
-  ``$offset`` If specified, [search will start][0] this number of
   characters counted from the beginning of the string. Unlike
   [FUNCTION:STRRPOS] and [FUNCTION:STRRIPOS], the offset cannot be
   negative.

RETURN VALUE
============

Returns the position of where the needle exists relative to the
beginning of the ``$haystack`` string (independent of offset). Also note
that string positions start at 0, and not 1. Returns [TYPE:FALSE] if the
needle was not found. [SNIPPET:RETURN.FALSEPROBLEM]

CHANGELOG
=========

\| Version \| Description
-------------------------

| 5.2.6 \| Something cool happened
| 5.2.2 \| If the ``$offset`` parameter indicates the position of a
negative truncation or beyond, false is returned. Other versions get the
string from start.

EXAMPLES
========

Using *===*: \`\`php \`\`

NOTES
=====

-  [NOTE:BIN-SAFE]

SEE ALSO
========

-  [FUNCTION:stripos]
-  [FUNCTION:strrpos]
-  [FUNCTION:strripos]
-  [FUNCTION:strstr]
-  [FUNCTION:strpbrk]
-  [FUNCTION:substr]
-  [FUNCTION:preg\_match]