[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 get-console-screenshot:


**********************
get-console-screenshot
**********************



===========
Description
===========



Retrieve a JPG-format screenshot of a running instance to help with troubleshooting.

 

The returned content is Base64-encoded.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/GetConsoleScreenshot>`_


========
Synopsis
========

::

    get-console-screenshot
  [--dry-run | --no-dry-run]
  --instance-id <value>
  [--wake-up | --no-wake-up]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the instance.

  

``--wake-up`` | ``--no-wake-up`` (boolean)


  When set to ``true`` , acts as keystroke input and wakes up an instance that's in standby or "sleep" mode.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ImageData -> (string)

  

  The data that comprises the image.

  

  

InstanceId -> (string)

  

  The ID of the instance.

  

  

