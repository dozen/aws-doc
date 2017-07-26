[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot describe-thing:


**************
describe-thing
**************



===========
Description
===========



Gets information about the specified thing.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/DescribeThing>`_


========
Synopsis
========

::

    describe-thing
  --thing-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-name`` (string)


  The name of the thing.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

defaultClientId -> (string)

  

  The default client ID.

  

  

thingName -> (string)

  

  The name of the thing.

  

  

thingTypeName -> (string)

  

  The thing type name.

  

  

attributes -> (map)

  

  The thing attributes.

  

  key -> (string)

    

    

  value -> (string)

    An attribute value for an Thing. An empty or null value in Update means that existing value for that attribute should be deleted. Empty and null values in create are ignored.

    

  

version -> (long)

  

  The current version of the thing record in the registry.

   

  .. note::

     

    To avoid unintentional changes to the information in the registry, you can pass the version information in the ``expectedVersion`` parameter of the ``update-thing`` and ``delete-thing`` calls.

     

  

  

