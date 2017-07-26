[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es list-domain-names:


*****************
list-domain-names
*****************



===========
Description
===========



Returns the name of all Elasticsearch domains owned by the current user's account. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/es-2015-01-01/ListDomainNames>`_


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

DomainNames -> (list)

  

  List of Elasticsearch domain names.

  

  (structure)

    

    DomainName -> (string)

      

      Specifies the ``DomainName`` .

      

      

    

  

