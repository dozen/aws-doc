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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DeleteLaunchConfiguration>`_


========
Synopsis
========

::

    delete-launch-configuration
  --launch-configuration-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--launch-configuration-name`` (string)


  The name of the launch configuration.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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