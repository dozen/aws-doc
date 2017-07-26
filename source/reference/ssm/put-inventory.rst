[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm put-inventory:


*************
put-inventory
*************



===========
Description
===========



Bulk update custom inventory items on one more instance. The request adds an inventory item, if it doesn't already exist, or updates an inventory item, if it does exist.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/PutInventory>`_


========
Synopsis
========

::

    put-inventory
  --instance-id <value>
  --items <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  One or more instance IDs where you want to add or update inventory items.

  

``--items`` (list)


  The inventory items that you want to add or update on instances.

  



Shorthand Syntax::

    TypeName=string,SchemaVersion=string,CaptureTime=string,ContentHash=string,Content=[{KeyName1=string,KeyName2=string},{KeyName1=string,KeyName2=string}] ...




JSON Syntax::

  [
    {
      "TypeName": "string",
      "SchemaVersion": "string",
      "CaptureTime": "string",
      "ContentHash": "string",
      "Content": [
        {"string": "string"
          ...}
        ...
      ]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To assign customer metadata to an instance**

This example assigns rack location information to an instance. There is no output if the command succeeds.

Command::

  aws ssm put-inventory --instance-id "i-0cb2b964d3e14fd9f" --items '[{"CaptureTime": "2016-08-22T10:01:01Z", "TypeName": "Custom:RackInfo", "Content":[{"RackLocation": "Bay B/Row C/Rack D/Shelf E"}], "SchemaVersion": "1.0"}]'
  

======
Output
======

