[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-devices:


************
list-devices
************



===========
Description
===========



Gets information about unique device types.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/ListDevices>`_


``list-devices`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``devices``


========
Synopsis
========

::

    list-devices
  [--arn <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The Amazon Resource Name (ARN) of the project.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

devices -> (list)

  

  Information about the devices.

  

  (structure)

    

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

      

      

    

  

nextToken -> (string)

  

  If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

  

  

