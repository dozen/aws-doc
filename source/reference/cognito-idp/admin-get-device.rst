[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp admin-get-device:


****************
admin-get-device
****************



===========
Description
===========



Gets the device, as an administrator.

 

Requires developer credentials.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/AdminGetDevice>`_


========
Synopsis
========

::

    admin-get-device
  --device-key <value>
  --user-pool-id <value>
  --username <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--device-key`` (string)


  The device key.

  

``--user-pool-id`` (string)


  The user pool ID.

  

``--username`` (string)


  The user name.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Device -> (structure)

  

  The device.

  

  DeviceKey -> (string)

    

    The device key.

    

    

  DeviceAttributes -> (list)

    

    The device attributes.

    

    (structure)

      

      Specifies whether the attribute is standard or custom.

      

      Name -> (string)

        

        The name of the attribute.

        

        

      Value -> (string)

        

        The value of the attribute.

        

        

      

    

  DeviceCreateDate -> (timestamp)

    

    The creation date of the device.

    

    

  DeviceLastModifiedDate -> (timestamp)

    

    The last modified date of the device.

    

    

  DeviceLastAuthenticatedDate -> (timestamp)

    

    The date in which the device was last authenticated.

    

    

  

