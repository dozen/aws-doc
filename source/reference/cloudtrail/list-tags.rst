[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail list-tags:


*********
list-tags
*********



===========
Description
===========



Lists the tags for the specified trail or trails in the current region.

 

Lists the tags for the trail in the current region.



========
Synopsis
========

::

    list-tags
  --resource-id-list <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-id-list`` (list)


  Specifies a list of trail ARNs whose tags will be listed. The list has a limit of 20 ARNs. The format of a trail ARN is ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail`` .

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  Reserved for future use.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ResourceTagList -> (list)

  

  A list of resource tags.

  

  (structure)

    

    A resource tag.

    

    ResourceId -> (string)

      

      Specifies the ARN of the resource.

      

      

    TagsList -> (list)

      

      A list of tags.

      

      (structure)

        

        A custom key-value pair associated with a resource such as a CloudTrail trail.

        

        Key -> (string)

          

          The key in a key-value pair. The key must be must be no longer than 128 Unicode characters. The key must be unique for the resource to which it applies.

          

          

        Value -> (string)

          

          The value in a key-value pair of a tag. The value must be no longer than 256 Unicode characters.

          

          

        

      

    

  

NextToken -> (string)

  

  Reserved for future use. 

  

  

