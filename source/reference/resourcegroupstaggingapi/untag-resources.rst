[ :ref:`aws <cli:aws>` . :ref:`resourcegroupstaggingapi <cli:aws resourcegroupstaggingapi>` ]

.. _cli:aws resourcegroupstaggingapi untag-resources:


***************
untag-resources
***************



===========
Description
===========



Removes the specified tags from the specified resources. When you specify a tag key, the action removes both that key and its associated value. The operation succeeds even if you attempt to remove tags from a resource that were already removed. Note the following:

 

 
* To remove tags from a resource, you need the necessary permissions for the service that the resource belongs to as well as permissions for removing tags. For more information, see `Obtaining Permissions for Tagging <http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/obtaining-permissions-for-tagging.html>`_ in the *AWS Resource Groups and Tag Editor User Guide* . 
 
* You can only tag resources that are located in the specified region for the AWS account. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/resourcegroupstaggingapi-2017-01-26/UntagResources>`_


========
Synopsis
========

::

    untag-resources
  --resource-arn-list <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn-list`` (list)


  A list of ARNs. An ARN (Amazon Resource Name) uniquely identifies a resource. You can specify a minimum of 1 and a maximum of 20 ARNs (resources) to untag. An ARN can be set to a maximum of 1600 characters. For more information, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* .

  



Syntax::

  "string" "string" ...



``--tag-keys`` (list)


  A list of the tag keys that you want to remove from the specified resources.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FailedResourcesMap -> (map)

  

  Details of resources that could not be untagged. An error code, status code, and error message are returned for each failed item.

  

  key -> (string)

    

    

  value -> (structure)

    

    Details of the common errors that all actions return.

    

    StatusCode -> (integer)

      

      The HTTP status code of the common error.

      

      

    ErrorCode -> (string)

      

      The code of the common error. Valid values include ``InternalServiceException`` , ``InvalidParameterException`` , and any valid error code returned by the AWS service that hosts the resource that you want to tag.

      

      

    ErrorMessage -> (string)

      

      The message of the common error.

      

      

    

  

