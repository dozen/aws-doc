[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 report-instance-status:


**********************
report-instance-status
**********************



===========
Description
===========



Submits feedback about the status of an instance. The instance must be in the ``running`` state. If your experience with the instance differs from the instance status returned by  describe-instance-status , use  report-instance-status to report your experience with the instance. Amazon EC2 collects this information to improve the accuracy of status checks.

 

Use of this action does not change the value returned by  describe-instance-status .



========
Synopsis
========

::

    report-instance-status
  [--dry-run | --no-dry-run]
  --instances <value>
  --status <value>
  [--start-time <value>]
  [--end-time <value>]
  --reason-codes <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instances`` (list)


  One or more instances.

  



Syntax::

  "string" "string" ...



``--status`` (string)


  The status of all instances listed.

  

  Possible values:

  
  *   ``ok``

  
  *   ``impaired``

  

  

``--start-time`` (timestamp)


  The time at which the reported instance health state began.

  

``--end-time`` (timestamp)


  The time at which the reported instance health state ended.

  

``--reason-codes`` (list)


  One or more reason codes that describes the health state of your instance.

   

   
  * ``instance-stuck-in-state`` : My instance is stuck in a state.
   
  * ``unresponsive`` : My instance is unresponsive.
   
  * ``not-accepting-credentials`` : My instance is not accepting my credentials.
   
  * ``password-not-available`` : A password is not available for my instance.
   
  * ``performance-network`` : My instance is experiencing performance problems which I believe are network related.
   
  * ``performance-instance-store`` : My instance is experiencing performance problems which I believe are related to the instance stores.
   
  * ``performance-ebs-volume`` : My instance is experiencing performance problems which I believe are related to an EBS volume.
   
  * ``performance-other`` : My instance is experiencing performance problems.
   
  * ``other`` : [explain using the description parameter]
   

  



Syntax::

  "string" "string" ...

  Where valid values are:
    instance-stuck-in-state
    unresponsive
    not-accepting-credentials
    password-not-available
    performance-network
    performance-instance-store
    performance-ebs-volume
    performance-other
    other





``--description`` (string)


  Descriptive text about the health state of your instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To report status feedback for an instance**

This example command reports status feedback for the specified instance.

Command::

  aws ec2 report-instance-status --instances i-570e5a28 --status impaired --reason-codes unresponsive


======
Output
======

None