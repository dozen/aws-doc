[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch list-domain-names:


*****************
list-domain-names
*****************



===========
Description
===========



Lists all search domains owned by an account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudsearch-2013-01-01/ListDomainNames>`_


========
Synopsis
========

::

    list-domain-names
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DomainNames -> (map)

  

  The names of the search domains owned by an account.

  

  key -> (string)

    

    A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

    

    

  value -> (string)

    

    The Amazon CloudSearch API version for a domain: 2011-02-01 or 2013-01-01.

    

    

  

