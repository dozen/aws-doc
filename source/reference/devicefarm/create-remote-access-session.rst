[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm create-remote-access-session:


****************************
create-remote-access-session
****************************



===========
Description
===========



Specifies and starts a remote access session.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/CreateRemoteAccessSession>`_


========
Synopsis
========

::

    create-remote-access-session
  --project-arn <value>
  --device-arn <value>
  [--name <value>]
  [--configuration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--project-arn`` (string)


  The Amazon Resource name (ARN) of the project for which you want to create a remote access session.

  

``--device-arn`` (string)


  The Amazon Resource name (ARN) of the device for which you want to create a remote access session.

  

``--name`` (string)


  The name of the remote access session that you wish to create.

  

``--configuration`` (structure)


  The configuration information for the remote access session request.

  



Shorthand Syntax::

    billingMethod=string




JSON Syntax::

  {
    "billingMethod": "METERED"|"UNMETERED"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

remoteAccessSession -> (structure)

  

  A container that describes the remote access session when the request to create a remote access session is sent.

  

  arn -> (string)

    

    The Amazon Resource name (ARN) of the remote access session.

    

    

  name -> (string)

    

    The name of the remote access session.

    

    

  created -> (timestamp)

    

    The date and time the remote access session was created.

    

    

  status -> (string)

    

    The status of the remote access session. Can be any of the following:

     

     
    * PENDING: A pending status. 
     
    * PENDING_CONCURRENCY: A pending concurrency status. 
     
    * PENDING_DEVICE: A pending device status. 
     
    * PROCESSING: A processing status. 
     
    * SCHEDULING: A scheduling status. 
     
    * PREPARING: A preparing status. 
     
    * RUNNING: A running status. 
     
    * COMPLETED: A completed status. 
     
    * STOPPING: A stopping status. 
     

    

    

  result -> (string)

    

    The result of the remote access session. Can be any of the following:

     

     
    * PENDING: A pending condition. 
     
    * PASSED: A passing condition. 
     
    * WARNED: A warning condition. 
     
    * FAILED: A failed condition. 
     
    * SKIPPED: A skipped condition. 
     
    * ERRORED: An error condition. 
     
    * STOPPED: A stopped condition. 
     

    

    

  message -> (string)

    

    A message about the remote access session.

    

    

  started -> (timestamp)

    

    The date and time the remote access session was started.

    

    

  stopped -> (timestamp)

    

    The date and time the remote access session was stopped.

    

    

  device -> (structure)

    

    The device (phone or tablet) used in the remote access session.

    

    arn -> (string)

      

      The device's ARN.

      

      

    name -> (string)

      

      The device's display name.

      

      

    manufacturer -> (string)

      

      The device's manufacturer name.

      

      

    model -> (string)

      

      The device's model name.

      

      

    formFactor -> (string)

      

      The device's form factor.

       

      Allowed values include:

       

       
      * PHONE: The phone form factor. 
       
      * TABLET: The tablet form factor. 
       

      

      

    platform -> (string)

      

      The device's platform.

       

      Allowed values include:

       

       
      * ANDROID: The Android platform. 
       
      * IOS: The iOS platform. 
       

      

      

    os -> (string)

      

      The device's operating system type.

      

      

    cpu -> (structure)

      

      Information about the device's CPU.

      

      frequency -> (string)

        

        The CPU's frequency.

        

        

      architecture -> (string)

        

        The CPU's architecture, for example x86 or ARM.

        

        

      clock -> (double)

        

        The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

        

        

      

    resolution -> (structure)

      

      The resolution of the device.

      

      width -> (integer)

        

        The screen resolution's width, expressed in pixels.

        

        

      height -> (integer)

        

        The screen resolution's height, expressed in pixels.

        

        

      

    heapSize -> (long)

      

      The device's heap size, expressed in bytes.

      

      

    memory -> (long)

      

      The device's total memory size, expressed in bytes.

      

      

    image -> (string)

      

      The device's image name.

      

      

    carrier -> (string)

      

      The device's carrier.

      

      

    radio -> (string)

      

      The device's radio.

      

      

    remoteAccessEnabled -> (boolean)

      

      Specifies whether remote access has been enabled for the specified device.

      

      

    fleetType -> (string)

      

      The type of fleet to which this device belongs. Possible values for fleet type are PRIVATE and PUBLIC.

      

      

    fleetName -> (string)

      

      The name of the fleet to which this device belongs.

      

      

    

  billingMethod -> (string)

    

    The billing method of the remote access session. Possible values include ``METERED`` or ``UNMETERED`` . For more information about metered devices, see `AWS Device Farm terminology <http://docs.aws.amazon.com/devicefarm/latest/developerguide/welcome.html#welcome-terminology>`_ ."

    

    

  deviceMinutes -> (structure)

    

    The number of minutes a device is used in a remote access sesssion (including setup and teardown minutes).

    

    total -> (double)

      

      When specified, represents the total minutes used by the resource to run tests.

      

      

    metered -> (double)

      

      When specified, represents only the sum of metered minutes used by the resource to run tests.

      

      

    unmetered -> (double)

      

      When specified, represents only the sum of unmetered minutes used by the resource to run tests.

      

      

    

  endpoint -> (string)

    

    The endpoint for the remote access sesssion.

    

    

  

