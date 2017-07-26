[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` . :ref:`wait <cli:aws ec2 wait>` ]

.. _cli:aws ec2 wait bundle-task-complete:


********************
bundle-task-complete
********************



===========
Description
===========

Wait until JMESPath query BundleTasks[].State returns complete for all elements when polling with ``describe-bundle-tasks``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

========
Synopsis
========

::

    bundle-task-complete
  [--dry-run | --no-dry-run]
  [--bundle-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--bundle-ids`` (list)


  One or more bundle task IDs.

   

  Default: Describes all your bundle tasks.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``bundle-id`` - The ID of the bundle task. 
   
  * ``error-code`` - If the task failed, the error code returned. 
   
  * ``error-message`` - If the task failed, the error message returned. 
   
  * ``instance-id`` - The ID of the instance. 
   
  * ``progress`` - The level of task completion, as a percentage (for example, 20%). 
   
  * ``s3-bucket`` - The Amazon S3 bucket to store the AMI. 
   
  * ``s3-prefix`` - The beginning of the AMI name. 
   
  * ``start-time`` - The time the task started (for example, 2013-09-15T17:15:20.000Z). 
   
  * ``state`` - The state of the task (``pending`` | ``waiting-for-shutdown`` | ``bundling`` | ``storing`` | ``cancelling`` | ``complete`` | ``failed`` ). 
   
  * ``update-time`` - The time of the most recent update for the task. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None