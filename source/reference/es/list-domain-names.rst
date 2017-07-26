[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es list-domain-names:


*****************
list-domain-names
*****************



===========
Description
===========



Returns the name of all Elasticsearch domains owned by the current user's account. 



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

DomainNames -> (list)

  

  List of Elasticsearch domain names.

  

  (structure)

    

    DomainName -> (string)

      

      Specifies the ``DomainName`` .

      

      

    

  

