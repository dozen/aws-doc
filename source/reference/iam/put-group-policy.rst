[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam put-group-policy:


****************
put-group-policy
****************



===========
Description
===========



Adds (or updates) an inline policy document that is embedded in the specified group. 

 

A user can also have managed policies attached to it. To attach a managed policy to a group, use  attach-group-policy . To create a new managed policy, use  create-policy . For information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 

 

For information about limits on the number of inline policies that you can embed in a group, see `Limitations on IAM Entities`_ in the *IAM User Guide* . 

 

.. note::

  Because policy documents can be large, you should use POST rather than GET when calling ``put-group-policy`` . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *Using IAM* guide. 



========
Synopsis
========

::

    put-group-policy
  --group-name <value>
  --policy-name <value>
  --policy-document <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--group-name`` (string)


  The name of the group to associate the policy with.

  

``--policy-name`` (string)


  The name of the policy document.

  

``--policy-document`` (string)


  The policy document.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To add a policy to a group**

The following ``put-group-policy`` command adds a policy to the IAM group named ``Admins``::

  aws iam put-group-policy --group-name Admins --policy-document file://AdminPolicy.json --policy-name AdminRoot

The policy is defined as a JSON document in the *AdminPolicy.json* file. (The file name and extension do not have
significance.)

For more information, see `Managing IAM Policies`_ in the *Using IAM* guide.

.. _`Managing IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingPolicies.html



======
Output
======

None

.. _Limitations on IAM Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html
.. _Making Query Requests: http://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_UsingQueryAPI.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
