[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-inventory-entries:


**********************
list-inventory-entries
**********************



===========
Description
===========



A list of inventory items returned by the request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/ListInventoryEntries>`_


========
Synopsis
========

::

    list-inventory-entries
  --instance-id <value>
  --type-name <value>
  [--filters <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The instance ID for which you want inventory information.

  

``--type-name`` (string)


  The type of inventory item for which you want information.

  

``--filters`` (list)


  One or more filters. Use a filter to return a more specific list of results.

  



Shorthand Syntax::

    Key=string,Values=string,string,Type=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Values": ["string", ...],
      "Type": "Equal"|"NotEqual"|"BeginWith"|"LessThan"|"GreaterThan"
    }
    ...
  ]



``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--max-results`` (integer)


  The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view custom inventory entries for an instance**

This example lists all the custom inventory entries for an instance.

Command::

  aws ssm list-inventory-entries --instance-id "i-0cb2b964d3e14fd9f" --type-name "Custom:RackInfo"

Output::

  {
	"InstanceId": "i-0cb2b964d3e14fd9f",
	"TypeName": "Custom:RackInfo",
	"Entries": [
		{
			"RackLocation": "Bay B/Row C/Rack D/Shelf E"
		}
	],
	"SchemaVersion": "1.0",
	"CaptureTime": "2016-08-22T10:01:01Z"
  }


======
Output
======

TypeName -> (string)

  

  The type of inventory item returned by the request.

  

  

InstanceId -> (string)

  

  The instance ID targeted by the request to query inventory information.

  

  

SchemaVersion -> (string)

  

  The inventory schema version used by the instance(s).

  

  

CaptureTime -> (string)

  

  The time that inventory information was collected for the instance(s).

  

  

Entries -> (list)

  

  A list of inventory items on the instance(s).

  

  (map)

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

