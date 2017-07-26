[ :ref:`aws <cli:aws>` . :ref:`resourcegroupstaggingapi <cli:aws resourcegroupstaggingapi>` ]

.. _cli:aws resourcegroupstaggingapi tag-resources:


*************
tag-resources
*************



===========
Description
===========



Applies one or more tags to the specified resources. Note the following:

 

 
* Not all resources can have tags. For a list of resources that support tagging, see `Supported Resources <http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/supported-resources.html>`_ in the *AWS Resource Groups and Tag Editor User Guide* . 
 
* Each resource can have up to 50 tags. For other limits, see `Tag Restrictions <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html#tag-restrictions>`_ in the *Amazon EC2 User Guide for Linux Instances* . 
 
* You can only tag resources that are located in the specified region for the AWS account. 
 
* To add tags to a resource, you need the necessary permissions for the service that the resource belongs to as well as permissions for adding tags. For more information, see `Obtaining Permissions for Tagging <http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/obtaining-permissions-for-tagging.html>`_ in the *AWS Resource Groups and Tag Editor User Guide* . 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/resourcegroupstaggingapi-2017-01-26/TagResources>`_


========
Synopsis
========

::

    tag-resources
  --resource-arn-list <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn-list`` (list)


  A list of ARNs. An ARN (Amazon Resource Name) uniquely identifies a resource. You can specify a minimum of 1 and a maximum of 20 ARNs (resources) to tag. An ARN can be set to a maximum of 1600 characters. For more information, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* .

  



Syntax::

  "string" "string" ...



``--tags`` (map)


  The tags that you want to add to the specified resources. A tag consists of a key and a value that you define.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FailedResourcesMap -> (map)

  

  Details of resources that could not be tagged. An error code, status code, and error message are returned for each failed item.

  

  key -> (string)

    

    

  value -> (structure)

    

    Details of the common errors that all actions return.

    

    StatusCode -> (integer)

      

      The HTTP status code of the common error.

      

      

    ErrorCode -> (string)

      

      The code of the common error. Valid values include ``InternalServiceException`` , ``InvalidParameterException`` , and any valid error code returned by the AWS service that hosts the resource that you want to tag.

      

      

    ErrorMessage -> (string)

      

      The message of the common error.

      

      

    

  

