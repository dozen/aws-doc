[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation signal-resource:


***************
signal-resource
***************



===========
Description
===========



Sends a signal to the specified resource with a success or failure status. You can use the signal-resource API in conjunction with a creation policy or update policy. AWS CloudFormation doesn't proceed with a stack creation or update until resources receive the required number of signals or the timeout period is exceeded. The signal-resource API is useful in cases where you want to send signals from anywhere other than an Amazon EC2 instance.



========
Synopsis
========

::

    signal-resource
  --stack-name <value>
  --logical-resource-id <value>
  --unique-id <value>
  --status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-name`` (string)


  The stack name or unique stack ID that includes the resource that you want to signal.

  

``--logical-resource-id`` (string)


  The logical ID of the resource that you want to signal. The logical ID is the name of the resource that given in the template.

  

``--unique-id`` (string)


  A unique ID of the signal. When you signal Amazon EC2 instances or Auto Scaling groups, specify the instance ID that you are signaling as the unique ID. If you send multiple signals to a single resource (such as signaling a wait condition), each signal requires a different unique ID.

  

``--status`` (string)


  The status of the signal, which is either success or failure. A failure signal causes AWS CloudFormation to immediately fail the stack creation or update.

  

  Possible values:

  
  *   ``SUCCESS``

  
  *   ``FAILURE``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None