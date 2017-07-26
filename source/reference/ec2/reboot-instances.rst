[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 reboot-instances:


****************
reboot-instances
****************



===========
Description
===========



Requests a reboot of one or more instances. This operation is asynchronous; it only queues a request to reboot the specified instances. The operation succeeds if the instances are valid and belong to you. Requests to reboot terminated instances are ignored.

 

If an instance does not cleanly shut down within four minutes, Amazon EC2 performs a hard reboot.

 

For more information about troubleshooting, see `Getting Console Output and Rebooting Instances <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-console.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/RebootInstances>`_


========
Synopsis
========

::

    reboot-instances
  --instance-ids <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-ids`` (list)


  One or more instance IDs.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To reboot an Amazon EC2 instance**

This example reboots the specified instance. If the command succeeds, no output is returned.

Command::

  aws ec2 reboot-instances --instance-ids i-1234567890abcdef5

For more information, see `Reboot Your Instance`_ in the *Amazon Elastic Compute Cloud User Guide*.

.. _`Reboot Your Instance`: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-reboot.html



======
Output
======

None