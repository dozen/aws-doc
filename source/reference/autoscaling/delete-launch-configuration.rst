[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling delete-launch-configuration:


***************************
delete-launch-configuration
***************************



===========
Description
===========



Deletes the specified launch configuration.

 

The launch configuration must not be attached to an Auto Scaling group. When this call completes, the launch configuration is no longer available for use.



========
Synopsis
========

::

    delete-launch-configuration
  --launch-configuration-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--launch-configuration-name`` (string)


  The name of the launch configuration.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a launch configuration**

This example deletes the specified launch configuration::

	aws autoscaling delete-launch-configuration --launch-configuration-name my-launch-config

For more information, see `Shut Down Auto Scaling Processes`_ in the *Auto Scaling Developer Guide*.

.. _`Shut Down Auto Scaling Processes`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-process-shutdown.html


======
Output
======

None