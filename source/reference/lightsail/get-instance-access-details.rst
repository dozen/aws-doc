[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-instance-access-details:


***************************
get-instance-access-details
***************************



===========
Description
===========



Returns temporary SSH keys you can use to connect to a specific virtual private server, or *instance* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetInstanceAccessDetails>`_


========
Synopsis
========

::

    get-instance-access-details
  --instance-name <value>
  [--protocol <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-name`` (string)


  The name of the instance to access.

  

``--protocol`` (string)


  The protocol to use to connect to your instance. Defaults to ``ssh`` .

  

  Possible values:

  
  *   ``ssh``

  
  *   ``rdp``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

accessDetails -> (structure)

  

  An array of key-value pairs containing information about a get instance access request.

  

  certKey -> (string)

    

    For SSH access, the public key to use when accessing your instance For OpenSSH clients (e.g., command line SSH), you should save this value to ``tempkey-cert.pub`` .

    

    

  expiresAt -> (timestamp)

    

    For SSH access, the date on which the temporary keys expire.

    

    

  ipAddress -> (string)

    

    The public IP address of the Amazon Lightsail instance.

    

    

  password -> (string)

    

    For RDP access, the temporary password of the Amazon EC2 instance.

    

    

  privateKey -> (string)

    

    For SSH access, the temporary private key. For OpenSSH clients (e.g., command line SSH), you should save this value to ``tempkey`` ).

    

    

  protocol -> (string)

    

    The protocol for these Amazon Lightsail instance access details.

    

    

  instanceName -> (string)

    

    The name of this Amazon Lightsail instance.

    

    

  username -> (string)

    

    The user name to use when logging in to the Amazon Lightsail instance.

    

    

  

