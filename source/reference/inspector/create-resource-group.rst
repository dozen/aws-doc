[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector create-resource-group:


*********************
create-resource-group
*********************



===========
Description
===========



Creates a resource group using the specified set of tags (key and value pairs) that are used to select the EC2 instances to be included in an Inspector application. The created resource group is then used to create an Inspector application.



========
Synopsis
========

::

    create-resource-group
  --resource-group-tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-group-tags`` (string)


  A collection of keys and an array of possible values in JSON format.

   

  For example, [{ "key1" : ["Value1","Value2"]},{"Key2": ["Value3"]}]

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

resourceGroupArn -> (string)

  

  The ARN specifying the resource group that is created.

  

  

