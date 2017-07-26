[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp update-group:


************
update-group
************



===========
Description
===========



Updates the specified group with the specified attributes.

 

Requires developer credentials.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/UpdateGroup>`_


========
Synopsis
========

::

    update-group
  --group-name <value>
  --user-pool-id <value>
  [--description <value>]
  [--role-arn <value>]
  [--precedence <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--group-name`` (string)


  The name of the group.

  

``--user-pool-id`` (string)


  The user pool ID for the user pool.

  

``--description`` (string)


  A string containing the new description of the group.

  

``--role-arn`` (string)


  The new role ARN for the group. This is used for setting the ``cognito:roles`` and ``cognito:preferred_role`` claims in the token.

  

``--precedence`` (integer)


  The new precedence value for the group. For more information about this parameter, see `create-group <API_CreateGroup.html>`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Group -> (structure)

  

  The group object for the group.

  

  GroupName -> (string)

    

    The name of the group.

    

    

  UserPoolId -> (string)

    

    The user pool ID for the user pool.

    

    

  Description -> (string)

    

    A string containing the description of the group.

    

    

  RoleArn -> (string)

    

    The role ARN for the group.

    

    

  Precedence -> (integer)

    

    A nonnegative integer value that specifies the precedence of this group relative to the other groups that a user can belong to in the user pool. If a user belongs to two or more groups, it is the group with the highest precedence whose role ARN will be used in the ``cognito:roles`` and ``cognito:preferred_role`` claims in the user's tokens. Groups with higher ``Precedence`` values take precedence over groups with lower ``Precedence`` values or with null ``Precedence`` values.

     

    Two groups can have the same ``Precedence`` value. If this happens, neither group takes precedence over the other. If two groups with the same ``Precedence`` have the same role ARN, that role is used in the ``cognito:preferred_role`` claim in tokens for users in each group. If the two groups have different role ARNs, the ``cognito:preferred_role`` claim is not set in users' tokens.

     

    The default ``Precedence`` value is null.

    

    

  LastModifiedDate -> (timestamp)

    

    The date the group was last modified.

    

    

  CreationDate -> (timestamp)

    

    The date the group was created.

    

    

  

