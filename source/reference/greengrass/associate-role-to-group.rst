[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass associate-role-to-group:


***********************
associate-role-to-group
***********************



===========
Description
===========

Associates a role with a group. The role will be used by the AWS Greengrass core in order to access AWS cloud services. The role's permissions will allow Greengrass core Lambda functions to perform actions against the cloud.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/AssociateRoleToGroup>`_


========
Synopsis
========

::

    associate-role-to-group
  --group-id <value>
  [--role-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--group-id`` (string)
The unique Id of the AWS Greengrass Group

``--role-arn`` (string)
Role arn you wish to associate with this group.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AssociatedAt -> (string)

  Time the role arn was associated to your group.

  

