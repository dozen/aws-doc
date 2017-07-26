[ :ref:`aws <cli:aws>` . :ref:`sdb <cli:aws sdb>` ]

.. _cli:aws sdb domain-metadata:


***************
domain-metadata
***************



===========
Description
===========



Returns information about the domain, including when the domain was created, the number of items and attributes in the domain, and the size of the attribute names and values. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sdb-2009-04-15/DomainMetadata>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.sdb true`` 



========
Synopsis
========

::

    domain-metadata
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)
The name of the domain for which to display the metadata of.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ItemCount -> (integer)

  The number of all items in the domain.

  

ItemNamesSizeBytes -> (long)

  The total size of all item names in the domain, in bytes.

  

AttributeNameCount -> (integer)

  The number of unique attribute names in the domain.

  

AttributeNamesSizeBytes -> (long)

  The total size of all unique attribute names in the domain, in bytes.

  

AttributeValueCount -> (integer)

  The number of all attribute name/value pairs in the domain.

  

AttributeValuesSizeBytes -> (long)

  The total size of all attribute values in the domain, in bytes.

  

Timestamp -> (integer)

  The data and time when metadata was calculated, in Epoch (UNIX) seconds.

  

