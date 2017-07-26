[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-tags:


*************
describe-tags
*************



===========
Description
===========



Describes one or more of the tags for your EC2 resources.

 

For more information about tags, see `Tagging Your Resources <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeTags>`_


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
  [--generate-cli-skeleton <value>]




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

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
              "ResourceId": "i-1234567890abcdef0",
              "Value": "Production",
              "Key": "Stack"
          },
          {
              "ResourceType": "instance",
              "ResourceId": "i-1234567890abcdef1",
              "Value": "Test",
              "Key": "Stack"
          },
          {
              "ResourceType": "instance",
              "ResourceId": "i-1234567890abcdef5",
              "Value": "Beta Server",
              "Key": "Name"
          },
          {
              "ResourceType": "volume",
              "ResourceId": "vol-049df61146c4d7901",
              "Value": "Project1",
              "Key": "Purpose"
          },
          {
              "ResourceType": "volume",
              "ResourceId": "vol-1234567890abcdef0",
              "Value": "Logs",
              "Key": "Purpose"
          }
      ]
  }

**To describe the tags for a single resource**

This example describes the tags for the specified instance.

Command::

  aws ec2 describe-tags --filters "Name=resource-id,Values=i-1234567890abcdef8"

Output::

  {
      "Tags": [
          {
              "ResourceType": "instance",
              "ResourceId": "i-1234567890abcdef8",
              "Value": "Test",
              "Key": "Stack"
          },
          {
              "ResourceType": "instance",
              "ResourceId": "i-1234567890abcdef8",
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
              "ResourceId": "vol-1234567890abcdef0",
              "Value": "Project1",
              "Key": "Purpose"
          },
          {
              "ResourceType": "volume",
              "ResourceId": "vol-049df61146c4d7901",
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
              "ResourceId": "i-1234567890abcdef8",
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
                "ResourceId": "i-1234567890abcdef5", 
                "Value": null, 
                "Key": "Purpose"
            }
        ]
    }



======
Output
======

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return..

  

  

Tags -> (list)

  

  A list of tags.

  

  (structure)

    

    Describes a tag.

    

    Key -> (string)

      

      The tag key.

      

      

    ResourceId -> (string)

      

      The ID of the resource. For example, ``ami-1a2b3c4d`` .

      

      

    ResourceType -> (string)

      

      The resource type.

      

      

    Value -> (string)

      

      The tag value.

      

      

    

  

