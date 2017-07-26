[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-key-pair:


***************
delete-key-pair
***************



===========
Description
===========



Deletes the specified key pair, by removing the public key from Amazon EC2.



========
Synopsis
========

::

    delete-key-pair
  [--dry-run | --no-dry-run]
  --key-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--key-name`` (string)


  The name of the key pair.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a key pair**

This example deletes the key pair named ``MyKeyPair``. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-key-pair --key-name MyKeyPair

For more information, see `Using Key Pairs`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Key Pairs`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-keypairs.html



======
Output
======

None