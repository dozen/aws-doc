[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-vtl-devices:


********************
describe-vtl-devices
********************



===========
Description
===========



Returns a description of virtual tape library (VTL) devices for the specified tape gateway. In the response, AWS Storage Gateway returns VTL device information.

 

This operation is only supported in the tape gateway architecture.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DescribeVTLDevices>`_


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
  [--generate-cli-skeleton <value>]




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

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

VTLDevices -> (list)

  

  An array of VTL device objects composed of the Amazon Resource Name(ARN) of the VTL devices.

  

  (structure)

    

    Represents a device object associated with a tape gateway.

    

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

  

  

