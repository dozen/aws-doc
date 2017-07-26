[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling set-instance-protection:


***********************
set-instance-protection
***********************



===========
Description
===========



Updates the instance protection settings of the specified instances.

 

For more information, see `Instance Protection <http://docs.aws.amazon.com/autoscaling/latest/userguide/as-instance-termination.html#instance-protection>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/SetInstanceProtection>`_


========
Synopsis
========

::

    set-instance-protection
  --instance-ids <value>
  --auto-scaling-group-name <value>
  --protected-from-scale-in | --no-protected-from-scale-in
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-ids`` (list)


  One or more instance IDs.

  



Syntax::

  "string" "string" ...



``--auto-scaling-group-name`` (string)


  The name of the group.

  

``--protected-from-scale-in`` | ``--no-protected-from-scale-in`` (boolean)


  Indicates whether the instance is protected from termination by Auto Scaling when scaling in.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change the instance protection setting for an instance**

This example enables instance protection for the specified instance::

    aws autoscaling set-instance-protection --instance-ids i-93633f9b --auto-scaling-group-name my-auto-scaling-group --protected-from-scale-in

This example disables instance protection for the specified instance::

    aws autoscaling set-instance-protection --instance-ids i-93633f9b --auto-scaling-group-name my-auto-scaling-group --no-protected-from-scale-in


======
Output
======

