[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-inventory-schema:


********************
get-inventory-schema
********************



===========
Description
===========



Return a list of inventory type names for the account, or return a list of attribute names for a specific Inventory item type. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetInventorySchema>`_


========
Synopsis
========

::

    get-inventory-schema
  [--type-name <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--type-name`` (string)


  The type of inventory item to return.

  

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

**To view your inventory schema**

This example returns a list of inventory type names for the account.

Command::

  aws ssm get-inventory-schema

Output::

  {
    "Schemas": [
        {
            "TypeName": "AWS:AWSComponent",
            "Version": "1.0",
            "Attributes": [
                {
                    "DataType": "STRING",
                    "Name": "Name"
                },
                {
                    "DataType": "STRING",
                    "Name": "ApplicationType"
                },
                {
                    "DataType": "STRING",
                    "Name": "Publisher"
                },
                {
                    "DataType": "STRING",
                    "Name": "Version"
                },
                {
                    "DataType": "STRING",
                    "Name": "InstalledTime"
                },
                {
                    "DataType": "STRING",
                    "Name": "Architecture"
                },
                {
                    "DataType": "STRING",
                    "Name": "URL"
                }
            ]
        },
        ...
	}
  }

======
Output
======

Schemas -> (list)

  

  Inventory schemas returned by the request.

  

  (structure)

    

    The inventory item schema definition. Users can use this to compose inventory query filters.

    

    TypeName -> (string)

      

      The name of the inventory type. Default inventory item type names start with AWS. Custom inventory type names will start with Custom. Default inventory item types include the following: AWS:AWSComponent, AWS:Application, AWS:InstanceInformation, AWS:Network, and AWS:WindowsUpdate.

      

      

    Version -> (string)

      

      The schema version for the inventory item.

      

      

    Attributes -> (list)

      

      The schema attributes for inventory. This contains data type and attribute name.

      

      (structure)

        

        Attributes are the entries within the inventory item content. It contains name and value.

        

        Name -> (string)

          

          Name of the inventory item attribute.

          

          

        DataType -> (string)

          

          The data type of the inventory item attribute. 

          

          

        

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

