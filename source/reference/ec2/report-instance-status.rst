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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ReportInstanceStatus>`_


========
Synopsis
========

::

    report-instance-status
  [--description <value>]
  [--dry-run | --no-dry-run]
  [--end-time <value>]
  --instances <value>
  --reason-codes <value>
  [--start-time <value>]
  --status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--description`` (string)


  Descriptive text about the health state of your instance.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--end-time`` (timestamp)


  The time at which the reported instance health state ended.

  

``--instances`` (list)


  One or more instances.

  



Syntax::

  "string" "string" ...



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





``--start-time`` (timestamp)


  The time at which the reported instance health state began.

  

``--status`` (string)


  The status of all instances listed.

  

  Possible values:

  
  *   ``ok``

  
  *   ``impaired``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To report status feedback for an instance**

This example command reports status feedback for the specified instance.

Command::

  aws ec2 report-instance-status --instances i-1234567890abcdef0 --status impaired --reason-codes unresponsive


======
Output
======

None