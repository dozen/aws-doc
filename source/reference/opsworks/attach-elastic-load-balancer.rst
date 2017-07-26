[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks attach-elastic-load-balancer:


****************************
attach-elastic-load-balancer
****************************



===========
Description
===========



Attaches an Elastic Load Balancing load balancer to a specified layer. For more information, see `Elastic Load Balancing`_ .

 

.. note::

   

  You must create the Elastic Load Balancing instance separately, by using the Elastic Load Balancing console, API, or CLI. For more information, see `Elastic Load Balancing Developer Guide`_ .

   

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    attach-elastic-load-balancer
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


  The ID of the layer that the Elastic Load Balancing instance is to be attached to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To attach a load balancer to a layer**

The following example attaches a load balancer, identified by its name, to a specified layer. ::

  aws opsworks --region us-east-1 attach-elastic-load-balancer --elastic-load-balancer-name Java-LB --layer-id 888c5645-09a5-4d0e-95a8-812ef1db76a4 

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
.. _Elastic Load Balancing Developer Guide: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/Welcome.html
.. _Elastic Load Balancing: http://docs.aws.amazon.com/opsworks/latest/userguide/load-balancer-elb.html
