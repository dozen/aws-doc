[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-tags:


*************
describe-tags
*************



===========
Description
===========



Describes one or more of the tags for your EC2 resources.

 

For more information about tags, see `Tagging Your Resources`_ in the *Amazon Elastic Compute Cloud User Guide* .



``describe-tags`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Tags``


========
Synopsis
========

::

    describe-tags
  [--dry-run | --no-dry-run]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--filters`` (list)


  One or more filters.

   

   
  * ``key`` - The tag key. 
   
  * ``resource-id`` - The resource ID. 
   
  * ``resource-type`` - The resource type (``customer-gateway`` | ``dhcp-options`` | ``image`` | ``instance`` | ``internet-gateway`` | ``network-acl`` | ``network-interface`` | ``reserved-instances`` | ``route-table`` | ``security-group`` | ``snapshot`` | ``spot-instances-request`` | ``subnet`` | ``volume`` | ``vpc`` | ``vpn-connection`` | ``vpn-gateway`` ). 
   
  * ``value`` - The tag value. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your tags**

This example describes the tags for all your resources.

Command::

  aws ec2 describe-tags

Output::

  {
      "Tags": [
          {
              "ResourceType": "image",
              "ResourceId": "ami-78a54011",
              "Value": "Production",
              "Key": "Stack"
          },
          {
              "ResourceType": "image",
              "ResourceId": "ami-3ac33653",
              "Value": "Test",
              "Key": "Stack"
          },
          {
              "ResourceType": "instance",
              "ResourceId": "i-12345678",
              "Value": "Production",
              "Key": "Stack"
          },
          {
              "ResourceType": "instance",
              "ResourceId": "i-5f4e3d2a",
              "Value": "Test",
              "Key": "Stack"
          },
          {
              "ResourceType": "instance",
              "ResourceId": "i-5f4e3d2a",
              "Value": "Beta Server",
              "Key": "Name"
          },
          {
              "ResourceType": "volume",
              "ResourceId": "vol-1a2b3c4d",
              "Value": "Project1",
              "Key": "Purpose"
          },
          {
              "ResourceType": "volume",
              "ResourceId": "vol-87654321",
              "Value": "Logs",
              "Key": "Purpose"
          }
      ]
  }

**To describe the tags for a single resource**

This example describes the tags for the specified instance.

Command::

  aws ec2 describe-tags --filters "Name=resource-id,Values=i-5f4e3d2a"

Output::

  {
      "Tags": [
          {
              "ResourceType": "instance",
              "ResourceId": "i-5f4e3d2a",
              "Value": "Test",
              "Key": "Stack"
          },
          {
              "ResourceType": "instance",
              "ResourceId": "i-5f4e3d2a",
              "Value": "Beta Server",
              "Key": "Name"
          }
      ]
  }

**To describe the tags for a type of resource**

This example describes the tags for your volumes.

Command::

  aws ec2 describe-tags --filters "Name=resource-type,Values=volume"

Output::

  {
      "Tags": [
          {
              "ResourceType": "volume",
              "ResourceId": "vol-1a2b3c4d",
              "Value": "Project1",
              "Key": "Purpose"
          },
          {
              "ResourceType": "volume",
              "ResourceId": "vol-87654321",
              "Value": "Logs",
              "Key": "Purpose"
          }
      ]
  }

**To describe the tags for your resources based on a key and a value**

This example describes the tags for your resources that have the key ``Stack`` and a value ``Test``.

Command::

  aws ec2 describe-tags --filters "Name=key,Values=Stack" "Name=value,Values=Test"

Output::

  {
      "Tags": [
          {
              "ResourceType": "image",
              "ResourceId": "ami-3ac33653",
              "Value": "Test",
              "Key": "Stack"
          },
          {
              "ResourceType": "instance",
              "ResourceId": "i-5f4e3d2a",
              "Value": "Test",
              "Key": "Stack"
          }
      ]
  }

This example describes the tags for all your instances that have a tag with the key ``Purpose`` and no value.

Command::

    aws ec2 describe-tags --filters "Name=resource-type,Values=instance" "Name=key,Values=Purpose" "Name=value,Values="
    
Output::

    {
        "Tags": [
            {
                "ResourceType": "instance", 
                "ResourceId": "i-1a2b3c4d", 
                "Value": null, 
                "Key": "Purpose"
            }
        ]
    }



======
Output
======

Tags -> (list)

  

  A list of tags.

  

  (structure)

    

    Describes a tag.

    

    ResourceId -> (string)

      

      The ID of the resource. For example, ``ami-1a2b3c4d`` .

      

      

    ResourceType -> (string)

      

      The resource type.

      

      

    Key -> (string)

      

      The tag key.

      

      

    Value -> (string)

      

      The tag value.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return..

  

  



.. _Tagging Your Resources: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html
