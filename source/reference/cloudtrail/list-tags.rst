[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail list-tags:


*********
list-tags
*********



===========
Description
===========



Lists the tags for the trail in the current region.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudtrail-2013-11-01/ListTags>`_


========
Synopsis
========

::

    list-tags
  --resource-id-list <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-id-list`` (list)


  Specifies a list of trail ARNs whose tags will be listed. The list has a limit of 20 ARNs. The format of a trail ARN is:

   

   ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail``  

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  Reserved for future use.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list the tags for a trail**

The following ``list-tags`` command lists the tags for ``Trail1`` and ``Trail2``::

  aws cloudtrail list-tags --resource-id-list arn:aws:cloudtrail:us-east-1:123456789012:trail/Trail1 arn:aws:cloudtrail:us-east-1:123456789012:trail/Trail2

Output::

  {
   "ResourceTagList": [
       {
           "ResourceId": "arn:aws:cloudtrail:us-east-1:123456789012:trail/Trail1", 
           "TagsList": [
               {
                   "Value": "Alice", 
                   "Key": "name"
               }, 
               {
                   "Value": "us", 
                   "Key": "location"
               }
           ]
       }, 
       {
           "ResourceId": "arn:aws:cloudtrail:us-east-1:123456789012:trail/Trail2", 
           "TagsList": [
               {
                   "Value": "Bob", 
                   "Key": "name"
               }
           ]
       }
    ]
  }

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

  

  

