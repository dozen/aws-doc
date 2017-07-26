[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-vtl-devices:


********************
describe-vtl-devices
********************



===========
Description
===========



Returns a description of virtual tape library (VTL) devices for the specified gateway. In the response, AWS Storage Gateway returns VTL device information. 

 

The list of VTL devices must be from one gateway.



``describe-vtl-devices`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``VTLDevices``


========
Synopsis
========

::

    describe-vtl-devices
  --gateway-arn <value>
  [--vtl-device-arns <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--vtl-device-arns`` (list)


  An array of strings, where each string represents the Amazon Resource Name (ARN) of a VTL device.

   

  .. note::

    All of the specified VTL devices must be from the same gateway. If no VTL devices are specified, the result will contain all devices on the specified gateway.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

VTLDevices -> (list)

  

  An array of VTL device objects composed of the Amazon Resource Name(ARN) of the VTL devices.

  

  (structure)

    

    Represents a device object associated with a gateway-VTL. 

    

    VTLDeviceARN -> (string)

      

      Specifies the unique Amazon Resource Name (ARN) of the device (tape drive or media changer).

      

      

    VTLDeviceType -> (string)

      

      

    VTLDeviceVendor -> (string)

      

      

    VTLDeviceProductIdentifier -> (string)

      

      

    DeviceiSCSIAttributes -> (structure)

      

      A list of iSCSI information about a VTL device.

      

      TargetARN -> (string)

        

        Specifies the unique Amazon Resource Name(ARN) that encodes the iSCSI qualified name(iqn) of a tape drive or media changer target.

        

        

      NetworkInterfaceId -> (string)

        

        The network interface identifier of the VTL device.

        

        

      NetworkInterfacePort -> (integer)

        

        The port used to communicate with iSCSI VTL device targets.

        

        

      ChapEnabled -> (boolean)

        

        Indicates whether mutual CHAP is enabled for the iSCSI target.

        

        

      

    

  

Marker -> (string)

  

  An opaque string that indicates the position at which the VTL devices that were fetched for description ended. Use the marker in your next request to fetch the next set of VTL devices in the list. If there are no more VTL devices to describe, this field does not appear in the response.

  

  

