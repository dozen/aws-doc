[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks detach-elastic-load-balancer:


****************************
detach-elastic-load-balancer
****************************



===========
Description
===========



Detaches a specified Elastic Load Balancing instance from its layer.

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    detach-elastic-load-balancer
  --elastic-load-balancer-name <value>
  --layer-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--elastic-load-balancer-name`` (string)


  The Elastic Load Balancing instance's name.

  

``--layer-id`` (string)


  The ID of the layer that the Elastic Load Balancing instance is attached to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To detach a load balancer from its layer**

The following example detaches a load balancer, identified by its name, from its layer. ::

  aws opsworks --region us-east-1 detach-elastic-load-balancer --elastic-load-balancer-name Java-LB --layer-id 888c5645-09a5-4d0e-95a8-812ef1db76a4 

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Elastic Load Balancing`_ in the *AWS OpsWorks User Guide*.

.. _`Elastic Load Balancing`: http://docs.aws.amazon.com/opsworks/latest/userguide/load-balancer-elb.html



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
