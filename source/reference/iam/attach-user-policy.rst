[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam attach-user-policy:


******************
attach-user-policy
******************



===========
Description
===========



Attaches the specified managed policy to the specified user.

 

You use this API to attach a *managed* policy to a user. To embed an inline policy in a user, use  put-user-policy .

 

For more information about policies, see `Managed Policies and Inline Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/AttachUserPolicy>`_


========
Synopsis
========

::

    attach-user-policy
  --user-name <value>
  --policy-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name (friendly name, not ARN) of the IAM user to attach the policy to.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--policy-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM policy you want to attach.

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attach a managed policy to an IAM user**

The following ``attach-user-policy`` command attaches the AWS managed policy named ``AdministratorAccess`` to the IAM user named ``Alice``::

  aws iam attach-user-policy --policy-arn arn:aws:iam::aws:policy/AdministratorAccess --user-name Alice

For more information, see `Managed Policies and Inline Policies`_ in the *Using IAM* guide.

.. _`Managed Policies and Inline Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html

======
Output
======

None