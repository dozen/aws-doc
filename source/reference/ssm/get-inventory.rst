[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-inventory:


*************
get-inventory
*************



===========
Description
===========



Query inventory information.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetInventory>`_


========
Synopsis
========

::

    get-inventory
  [--filters <value>]
  [--result-attributes <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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



``--result-attributes`` (list)


  The list of inventory item types to return.

  



Shorthand Syntax::

    TypeName=string ...




JSON Syntax::

  [
    {
      "TypeName": "string"
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

**To view your inventory**

This example gets the custom metadata for your inventory.

Command::

  aws ssm get-inventory

Output::

  {
    "Entities": [
        {
            "Data": {
                "AWS:InstanceInformation": {
                    "Content": [
                        {
                            "ComputerName": "ip-172-31-44-222.us-west-2.compute.internal",
                            "InstanceId": "i-0cb2b964d3e14fd9f",
                            "IpAddress": "172.31.44.222",
                            "AgentType": "amazon-ssm-agent",
                            "ResourceType": "EC2Instance",
                            "AgentVersion": "2.0.672.0",
                            "PlatformVersion": "2016.09",
                            "PlatformName": "Amazon Linux AMI",
                            "PlatformType": "Linux"
                        }
                    ],
                    "TypeName": "AWS:InstanceInformation",
                    "SchemaVersion": "1.0",
                    "CaptureTime": "2017-02-20T18:03:58Z"
                }
            },
            "Id": "i-0cb2b964d3e14fd9f"
        }
    ]
  }


======
Output
======

Entities -> (list)

  

  Collection of inventory entities such as a collection of instance inventory. 

  

  (structure)

    

    Inventory query results.

    

    Id -> (string)

      

      ID of the inventory result entity. For example, for managed instance inventory the result will be the managed instance ID. For EC2 instance inventory, the result will be the instance ID. 

      

      

    Data -> (map)

      

      The data section in the inventory result entity json.

      

      key -> (string)

        

        

      value -> (structure)

        

        The inventory result item.

        

        TypeName -> (string)

          

          The name of the inventory result item type.

          

          

        SchemaVersion -> (string)

          

          The schema version for the inventory result item/

          

          

        CaptureTime -> (string)

          

          The time inventory item data was captured.

          

          

        ContentHash -> (string)

          

          MD5 hash of the inventory item type contents. The content hash is used to determine whether to update inventory information. The put-inventory API does not update the inventory item type contents if the MD5 hash has not changed since last update. 

          

          

        Content -> (list)

          

          Contains all the inventory data of the item type. Results include attribute names and values. 

          

          (map)

            

            key -> (string)

              

              

            value -> (string)

              

              

            

          

        

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

