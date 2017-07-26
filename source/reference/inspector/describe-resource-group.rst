[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-resource-group:


***********************
describe-resource-group
***********************



===========
Description
===========



Describes the resource group specified by the resource group ARN.



========
Synopsis
========

::

    describe-resource-group
  --resource-group-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-group-arn`` (string)


  The ARN specifying the resource group that you want to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

resourceGroup -> (structure)

  

  Information about the resource group.

  

  resourceGroupArn -> (string)

    

    The ARN of the resource group. 

    

    

  resourceGroupTags -> (string)

    

    The tags (key and value pairs) of the resource group.

     

    This data type property is used in the  create-resource-group action.

     

    A collection of keys and an array of possible values in JSON format.

     

    For example, [{ "key1" : ["Value1","Value2"]},{"Key2": ["Value3"]}]

    

    

  

