[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot describe-thing-type:


*******************
describe-thing-type
*******************



===========
Description
===========



Gets information about the specified thing type.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/DescribeThingType>`_


========
Synopsis
========

::

    describe-thing-type
  --thing-type-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-type-name`` (string)


  The name of the thing type.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

thingTypeName -> (string)

  

  The name of the thing type.

  

  

thingTypeProperties -> (structure)

  

  The ThingTypeProperties contains information about the thing type including description, and a list of searchable thing attribute names.

  

  thingTypeDescription -> (string)

    

    The description of the thing type.

    

    

  searchableAttributes -> (list)

    

    A list of searchable thing attribute names.

    

    (string)

      

      

    

  

thingTypeMetadata -> (structure)

  

  The ThingTypeMetadata contains additional information about the thing type including: creation date and time, a value indicating whether the thing type is deprecated, and a date and time when it was deprecated.

  

  deprecated -> (boolean)

    

    Whether the thing type is deprecated. If **true** , no new things could be associated with this type.

    

    

  deprecationDate -> (timestamp)

    

    The date and time when the thing type was deprecated.

    

    

  creationDate -> (timestamp)

    

    The date and time when the thing type was created.

    

    

  

