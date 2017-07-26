[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch list-domain-names:


*****************
list-domain-names
*****************



===========
Description
===========



Lists all search domains owned by an account.



========
Synopsis
========

::

    list-domain-names
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DomainNames -> (map)

  

  The names of the search domains owned by an account.

  

  key -> (string)

    

    A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

    

    

  value -> (string)

    

    The Amazon CloudSearch API version for a domain: 2011-02-01 or 2013-01-01.

    

    

  

