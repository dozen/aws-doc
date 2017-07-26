[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-id-format:


******************
describe-id-format
******************



===========
Description
===========



Describes the ID format settings for your resources on a per-region basis, for example, to view which resource types are enabled for longer IDs. This request only returns information about resource types whose ID formats can be modified; it does not return information about other resource types. 

 

The following resource types support longer IDs: ``instance`` | ``reservation`` . 

 

These settings apply to the IAM user who makes the request; they do not apply to the entire AWS account. By default, an IAM user defaults to the same settings as the root user, unless they explicitly override the settings by running the  modify-id-format command. Resources created with longer IDs are visible to all IAM users, regardless of these settings and provided that they have permission to use the relevant ``Describe`` command for the resource type.



========
Synopsis
========

::

    describe-id-format
  [--resource <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource`` (string)


  The type of resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe the ID format for your resources**

This example describes the ID format for all resource types that support longer IDs. The output indicates that the ``instance`` and ``reservation`` resource types can be enabled or disabled for longer IDs. The ``reservation`` resource is already enabled. The ``Deadline`` field indicates the date (in UTC) at which you're automatically switched over to using longer IDs for that resource type. If a deadline is not yet available for the resource type, this value is not returned.

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

    

    Resource -> (string)

      

      The type of resource.

      

      

    UseLongIds -> (boolean)

      

      Indicates whether longer IDs (17-character IDs) are enabled for the resource.

      

      

    Deadline -> (timestamp)

      

      The date in UTC at which you are permanently switched over to using longer IDs.

      

      

    

  

