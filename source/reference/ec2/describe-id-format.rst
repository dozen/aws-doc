[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-id-format:


******************
describe-id-format
******************



===========
Description
===========



Describes the ID format settings for your resources on a per-region basis, for example, to view which resource types are enabled for longer IDs. This request only returns information about resource types whose ID formats can be modified; it does not return information about other resource types.

 

The following resource types support longer IDs: ``instance`` | ``reservation`` | ``snapshot`` | ``volume`` . 

 

These settings apply to the IAM user who makes the request; they do not apply to the entire AWS account. By default, an IAM user defaults to the same settings as the root user, unless they explicitly override the settings by running the  modify-id-format command. Resources created with longer IDs are visible to all IAM users, regardless of these settings and provided that they have permission to use the relevant ``Describe`` command for the resource type.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeIdFormat>`_


========
Synopsis
========

::

    describe-id-format
  [--resource <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource`` (string)


  The type of resource: ``instance`` | ``reservation`` | ``snapshot`` | ``volume``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the ID format for your resources**

This example describes the ID format for all resource types that support longer IDs. The output indicates that the ``instance``, ``reservation``, ``volume``, and ``snapshot`` resource types can be enabled or disabled for longer IDs. The ``reservation`` resource is already enabled. The ``Deadline`` field indicates the date (in UTC) at which you're automatically switched over to using longer IDs for that resource type. If a deadline is not yet available for the resource type, this value is not returned.

Command::

  aws ec2 describe-id-format

Output::

  {
    "Statuses": [
      {
        "Deadline": "2016-11-01T13:00:00.000Z",
        "UseLongIds": false,
        "Resource": "instance"
      },
      {
        "Deadline": "2016-11-01T13:00:00.000Z",
        "UseLongIds": true,
        "Resource": "reservation"
      },
      {
        "Deadline": "2016-11-01T13:00:00.000Z",
        "UseLongIds": false,
        "Resource": "volume"
      },
      {
        "Deadline": "2016-11-01T13:00:00.000Z",
        "UseLongIds": false,
        "Resource": "snapshot"
      }
    ]
  }

======
Output
======

Statuses -> (list)

  

  Information about the ID format for the resource.

  

  (structure)

    

    Describes the ID format for a resource.

    

    Deadline -> (timestamp)

      

      The date in UTC at which you are permanently switched over to using longer IDs. If a deadline is not yet available for this resource type, this field is not returned.

      

      

    Resource -> (string)

      

      The type of resource.

      

      

    UseLongIds -> (boolean)

      

      Indicates whether longer IDs (17-character IDs) are enabled for the resource.

      

      

    

  

