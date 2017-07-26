[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 get-console-output:


******************
get-console-output
******************



===========
Description
===========



Gets the console output for the specified instance.

 

Instances do not have a physical monitor through which you can view their console output. They also lack physical controls that allow you to power up, reboot, or shut them down. To allow these actions, we provide them through the Amazon EC2 API and command line interface.

 

Instance console output is buffered and posted shortly after instance boot, reboot, and termination. Amazon EC2 preserves the most recent 64 KB output which is available for at least one hour after the most recent post.

 

For Linux instances, the instance console output displays the exact console output that would normally be displayed on a physical monitor attached to a computer. This output is buffered because the instance produces it and then posts it to a store where the instance's owner can retrieve it.

 

For Windows instances, the instance console output includes output from the EC2Config service.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/GetConsoleOutput>`_


========
Synopsis
========

::

    get-console-output
  --instance-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The ID of the instance.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the console output**

This example gets the console ouput for the specified Linux instance.

Command::

  aws ec2 get-console-output --instance-id i-1234567890abcdef0

Output::

  {
      "InstanceId": "i-1234567890abcdef0",
      "Timestamp": "2013-07-25T21:23:53.000Z",
      "Output": "..."
  }



======
Output
======

InstanceId -> (string)

  

  The ID of the instance.

  

  

Output -> (string)

  

  The console output, Base64-encoded. If using a command line tool, the tool decodes the output for you.

  

  

Timestamp -> (timestamp)

  

  The time the output was last updated.

  

  

