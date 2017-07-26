[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks get-hostname-suggestion:


***********************
get-hostname-suggestion
***********************



===========
Description
===========



Gets a generated host name for the specified layer, based on the current host name theme.

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    get-hostname-suggestion
  --layer-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--layer-id`` (string)


  The layer ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get the next hostname for a layer**

The following example gets the next generated hostname for a specified layer. The layer used for
this example is a Java Application Server layer with one instance. The stack's hostname theme is
the default, Layer_Dependent. ::

  aws opsworks --region us-east-1 get-hostname-suggestion --layer-id 888c5645-09a5-4d0e-95a8-812ef1db76a4

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*::

  {
    "Hostname": "java-app2", 
    "LayerId": "888c5645-09a5-4d0e-95a8-812ef1db76a4"
  }

**More Information**

For more information, see `Create a New Stack`_ in the *AWS OpsWorks User Guide*.

.. _`Create a New Stack`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-creating.html



======
Output
======

LayerId -> (string)

  

  The layer ID.

  

  

Hostname -> (string)

  

  The generated host name.

  

  



.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
