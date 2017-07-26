[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-device:


**********
get-device
**********



===========
Description
===========



Gets information about a unique device type.



========
Synopsis
========

::

    get-device
  --arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--arn`` (string)


  The device type's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

device -> (structure)

  

  Represents a device type that an app is tested against.

  

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

    

    Represents the screen resolution of a device in height and width, expressed in pixels.

    

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

    

    

  

