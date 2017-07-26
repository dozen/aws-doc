[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot update-thing:


************
update-thing
************



===========
Description
===========



Updates the data for a thing.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/UpdateThing>`_


========
Synopsis
========

::

    update-thing
  --thing-name <value>
  [--thing-type-name <value>]
  [--attribute-payload <value>]
  [--expected-version <value>]
  [--remove-thing-type | --no-remove-thing-type]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-name`` (string)


  The name of the thing to update.

  

``--thing-type-name`` (string)


  The name of the thing type.

  

``--attribute-payload`` (structure)


  A list of thing attributes, a JSON string containing name-value pairs. For example:

   

   ``{\"attributes\":{\"name1\":\"value2\"}}``  

   

  This data is used to add new attributes or update existing attributes.

  



Shorthand Syntax::

    attributes={KeyName1=string,KeyName2=string},merge=boolean




JSON Syntax::

  {
    "attributes": {"string": "string"
      ...},
    "merge": true|false
  }



``--expected-version`` (long)


  The expected version of the thing record in the registry. If the version of the record in the registry does not match the expected version specified in the request, the ``update-thing`` request is rejected with a ``VersionConflictException`` .

  

``--remove-thing-type`` | ``--no-remove-thing-type`` (boolean)


  Remove a thing type association. If **true** , the assocation is removed.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

