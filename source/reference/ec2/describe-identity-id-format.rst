[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-identity-id-format:


***************************
describe-identity-id-format
***************************



===========
Description
===========



Describes the ID format settings for resources for the specified IAM user, IAM role, or root user. For example, you can view the resource types that are enabled for longer IDs. This request only returns information about resource types whose ID formats can be modified; it does not return information about other resource types. For more information, see `Resource IDs <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/resource-ids.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . 

 

The following resource types support longer IDs: ``instance`` | ``reservation`` | ``snapshot`` | ``volume`` . 

 

These settings apply to the principal specified in the request. They do not apply to the principal that makes the request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeIdentityIdFormat>`_


========
Synopsis
========

::

    describe-identity-id-format
  --principal-arn <value>
  [--resource <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--principal-arn`` (string)


  The ARN of the principal, which can be an IAM role, IAM user, or the root user.

  

``--resource`` (string)


  The type of resource: ``instance`` | ``reservation`` | ``snapshot`` | ``volume``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the ID format for an IAM role**

This example describes the ID format of the ``instance`` resource for the IAM role ``EC2Role`` in your AWS account. The output indicates that instances are enabled for longer IDs - instances created by this role receive longer IDs.

Command::

  aws ec2 describe-identity-id-format --principal-arn arn:aws:iam::123456789012:role/EC2Role --resource instance

Output::

  {
      "Statuses": [
          {
              "UseLongIds": true, 
              "Resource": "instance"
          }
      ]
  }

**To describe the ID format for an IAM user**

This example describes the ID format of the ``snapshot`` resource for the IAM user ``AdminUser`` in your AWS account. The output indicates that snapshots are enabled for longer IDs - snapshots created by this user receive longer IDs.

Command::

  aws ec2 describe-identity-id-format --principal-arn arn:aws:iam::123456789012:user/AdminUser --resource snapshot

Output::

  {
      "Statuses": [
          {
              "UseLongIds": true, 
              "Resource": "snapshot"
          }
      ]
  }

======
Output
======

Statuses -> (list)

  

  Information about the ID format for the resources.

  

  (structure)

    

    Describes the ID format for a resource.

    

    Deadline -> (timestamp)

      

      The date in UTC at which you are permanently switched over to using longer IDs. If a deadline is not yet available for this resource type, this field is not returned.

      

      

    Resource -> (string)

      

      The type of resource.

      

      

    UseLongIds -> (boolean)

      

      Indicates whether longer IDs (17-character IDs) are enabled for the resource.

      

      

    

  

