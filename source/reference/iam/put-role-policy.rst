[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam put-role-policy:


***************
put-role-policy
***************



===========
Description
===========



Adds (or updates) an inline policy document that is embedded in the specified role. 

 

When you embed an inline policy in a role, the inline policy is used as the role's access (permissions) policy. The role's trust policy is created at the same time as the role, using  create-role . You can update a role's trust policy using  update-assume-role-policy . For more information about roles, go to `Using Roles to Delegate Permissions and Federate Identities`_ . 

 

A role can also have a managed policy attached to it. To attach a managed policy to a role, use  attach-role-policy . To create a new managed policy, use  create-policy . For information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 

 

For information about limits on the number of inline policies that you can embed with a role, see `Limitations on IAM Entities`_ in the *IAM User Guide* . 

 

.. note::

  Because policy documents can be large, you should use POST rather than GET when calling ``put-role-policy`` . For general information about using the Query API with IAM, go to `Making Query Requests`_ in the *Using IAM* guide. 



========
Synopsis
========

::

    put-role-policy
  --role-name <value>
  --policy-name <value>
  --policy-document <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--role-name`` (string)


  The name of the role to associate the policy with.

  

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

**To attach a permissions policy to an IAM role**

The following ``put-role-policy`` command adds a permissions policy to the role named ``Test-Role``::

  aws iam put-role-policy --role-name Test-Role --policy-name ExamplePolicy --policy-document file://AdminPolicy.json

The policy is defined as a JSON document in the *AdminPolicy.json* file. (The file name and extension do not have significance.)

To attach a trust policy to a role, use the ``update-assume-role-policy`` command.

For more information, see `Creating a Role`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html



======
Output
======

None

.. _Limitations on IAM Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html
.. _Using Roles to Delegate Permissions and Federate Identities: http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-toplevel.html
.. _Making Query Requests: http://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_UsingQueryAPI.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
