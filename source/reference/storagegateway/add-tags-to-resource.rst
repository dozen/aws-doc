[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway add-tags-to-resource:


********************
add-tags-to-resource
********************



===========
Description
===========



This operation adds one or more tags to the specified resource. You use tags to add metadata to resources, which you can use to categorize these resources. For example, you can categorize resources by purpose, owner, environment, or team. Each tag consists of a key and a value, which you define. You can add tags to the following AWS Storage Gateway resources:

 

 
* Storage gateways of all types
 

 

 
* Storage Volumes
 

 

 
* Virtual Tapes
 

 

You can create a maximum of 10 tags for each resource. Virtual tapes and storage volumes that are recovered to a new gateway maintain their tags.



========
Synopsis
========

::

    add-tags-to-resource
  --resource-arn <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-arn`` (string)


  The Amazon Resource Name (ARN) of the resource you want to add tags to.

  

``--tags`` (list)


  The key-value pair that represents the tag you want to add to the resource. The value can be an empty string.

   

  .. note::

    

    Valid characters for key and value are letters, spaces, and numbers representable in UTF-8 format, and the following special characters: + - = . _ : / @.

    

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ResourceARN -> (string)

  

  The Amazon Resource Name (ARN) of the resource you want to add tags to.

  

  

