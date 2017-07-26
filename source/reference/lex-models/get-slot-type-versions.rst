[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-slot-type-versions:


**********************
get-slot-type-versions
**********************



===========
Description
===========



Gets information about all versions of a slot type.

 

The ``get-slot-type-versions`` operation returns a ``SlotTypeMetadata`` object for each version of a slot type. For example, if a slot type has three numbered versions, the ``get-slot-type-versions`` operation returns four ``SlotTypeMetadata`` objects in the response, one for each numbered version and one for the ``$LATEST`` version. 

 

The ``get-slot-type-versions`` operation always returns at least one version, the ``$LATEST`` version.

 

This operation requires permissions for the ``lex:GetSlotTypeVersions`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetSlotTypeVersions>`_


========
Synopsis
========

::

    get-slot-type-versions
  --name <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the slot type for which versions should be returned.

  

``--next-token`` (string)


  A pagination token for fetching the next page of slot type versions. If the response to this call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of versions, specify the pagination token in the next request. 

  

``--max-results`` (integer)


  The maximum number of slot type versions to return in the response. The default is 10.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

slotTypes -> (list)

  

  An array of ``SlotTypeMetadata`` objects, one for each numbered version of the slot type plus one for the ``$LATEST`` version.

  

  (structure)

    

    Provides information about a slot type..

    

    name -> (string)

      

      The name of the slot type.

      

      

    description -> (string)

      

      A description of the slot type.

      

      

    lastUpdatedDate -> (timestamp)

      

      The date that the slot type was updated. When you create a resource, the creation date and last updated date are the same. 

      

      

    createdDate -> (timestamp)

      

      The date that the slot type was created.

      

      

    version -> (string)

      

      The version of the slot type.

      

      

    

  

nextToken -> (string)

  

  A pagination token for fetching the next page of slot type versions. If the response to this call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of versions, specify the pagination token in the next request. 

  

  

