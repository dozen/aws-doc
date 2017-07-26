[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 get-password-data:


*****************
get-password-data
*****************



===========
Description
===========



Retrieves the encrypted administrator password for an instance running Windows.

 

The Windows password is generated at boot if the ``EC2Config`` service plugin, ``Ec2SetPassword`` , is enabled. This usually only happens the first time an AMI is launched, and then ``Ec2SetPassword`` is automatically disabled. The password is not generated for rebundled AMIs unless ``Ec2SetPassword`` is enabled before bundling.

 

The password is encrypted using the key pair that you specified when you launched the instance. You must provide the corresponding key pair file.

 

Password generation and encryption takes a few moments. We recommend that you wait up to 15 minutes after launching an instance before trying to retrieve the generated password.



========
Synopsis
========

::

    get-password-data
  [--dry-run | --no-dry-run]
  --instance-id <value>
  [--priv-launch-key <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the Windows instance.

  

``--priv-launch-key`` (string)


  The file that contains the private key used to launch the instance (e.g. windows-keypair.pem). If this is supplied, the password data sent from EC2 will be decrypted before display.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get the encrypted password**

This example gets the encrypted password.

Command::

  aws ec2 get-password-data --instance-id i-5203422c

Output::

  {
      "InstanceId": "i-5203422c",
      "Timestamp": "2013-08-07T22:18:38.000Z",
      "PasswordData": "gSlJFq+VpcZXqy+iktxMF6NyxQ4qCrT4+gaOuNOenX1MmgXPTj7XEXAMPLE
  UQ+YeFfb+L1U4C4AKv652Ux1iRB3CPTYP7WmU3TUnhsuBd+p6LVk7T2lKUml6OXbk6WPW1VYYm/TRPB1
  e1DQ7PY4an/DgZT4mwcpRFigzhniQgDDeO1InvSDcwoUTwNs0Y1S8ouri2W4n5GNlriM3Q0AnNVelVz/
  53TkDtxbNoU606M1gK9zUWSxqEgwvbV2j8c5rP0WCuaMWSFl4ziDu4bd7q+4RSyi8NUsVWnKZ4aEZffu
  DPGzKrF5yLlf3etP2L4ZR6CvG7K1hx7VKOQVN32Dajw=="
  }

**To get the decrypted password**

This example gets the decrypted password.

Command::

  aws ec2 get-password-data --instance-id  i-5203422c --priv-launch-key C:\Keys\MyKeyPair.pem

Output::

  {
      "InstanceId": "i-5203422c",
      "Timestamp": "2013-08-30T23:18:05.000Z",
      "PasswordData": "&ViJ652e*u"
  }



======
Output
======

InstanceId -> (string)

  

  The ID of the Windows instance.

  

  

Timestamp -> (timestamp)

  

  The time the data was last updated.

  

  

PasswordData -> (string)

  

  The password of the instance.

  

  

