[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass associate-service-role-to-account:


*********************************
associate-service-role-to-account
*********************************



===========
Description
===========

Associates a role which is used by AWS Greengrass. AWS Greengrass uses the role to access your Lambda functions and AWS IoT resources. This is necessary for deployments to succeed. It needs to have minimum permissions in policy ``AWSGreengrassResourceAccessRolePolicy``

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/AssociateServiceRoleToAccount>`_


========
Synopsis
========

::

    associate-service-role-to-account
  [--role-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-arn`` (string)
Role arn you wish to associate with this account.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AssociatedAt -> (string)

  Time when the service role was associated to the account.

  

