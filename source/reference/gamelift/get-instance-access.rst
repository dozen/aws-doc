[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift get-instance-access:


*******************
get-instance-access
*******************



===========
Description
===========



Requests remote access to a fleet instance. Remote access is useful for debugging, gathering benchmarking data, or watching activity in real time. 

 

Access requires credentials that match the operating system of the instance. For a Windows instance, Amazon GameLift returns a user name and password as strings for use with a Windows Remote Desktop client. For a Linux instance, Amazon GameLift returns a user name and RSA private key, also as strings, for use with an SSH client. The private key must be saved in the proper format to a ``.pem`` file before using. If you're making this request using the AWS CLI, saving the secret can be handled as part of the get-instance-access request. (See the example later in this topic). For more information on remote access, see `Remotely Accessing an Instance <http://docs.aws.amazon.com/gamelift/latest/developerguide/fleets-remote-access.html>`_ .

 

To request access to a specific instance, specify the IDs of the instance and the fleet it belongs to. If successful, an  InstanceAccess object is returned containing the instance's IP address and a set of credentials.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/GetInstanceAccess>`_


========
Synopsis
========

::

    get-instance-access
  --fleet-id <value>
  --instance-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet that contains the instance you want access to. The fleet can be in any of the following statuses: ``ACTIVATING`` , ``ACTIVE`` , or ``ERROR`` . Fleets with an ``ERROR`` status may be accessible for a short time before they are deleted.

  

``--instance-id`` (string)


  Unique identifier for an instance you want to get access to. You can access an instance in any status.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

InstanceAccess -> (structure)

  

  Object that contains connection information for a fleet instance, including IP address and access credentials.

  

  FleetId -> (string)

    

    Unique identifier for a fleet containing the instance being accessed.

    

    

  InstanceId -> (string)

    

    Unique identifier for an instance being accessed.

    

    

  IpAddress -> (string)

    

    IP address assigned to the instance.

    

    

  OperatingSystem -> (string)

    

    Operating system that is running on the instance.

    

    

  Credentials -> (structure)

    

    Credentials required to access the instance.

    

    UserName -> (string)

      

      User login string.

      

      

    Secret -> (string)

      

      Secret string. For Windows instances, the secret is a password for use with Windows Remote Desktop. For Linux instances, it is a private key (which must be saved as a ``.pem`` file) for use with SSH.

      

      

    

  

