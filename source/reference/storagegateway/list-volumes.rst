[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway list-volumes:


************
list-volumes
************



===========
Description
===========



Lists the iSCSI stored volumes of a gateway. Results are sorted by volume ARN. The response includes only the volume ARNs. If you want additional volume information, use the  describe-stored-iscsi-volumes or the  describe-cached-iscsi-volumes API.

 

The operation supports pagination. By default, the operation returns a maximum of up to 100 volumes. You can optionally specify the ``Limit`` field in the body to limit the number of volumes in the response. If the number of volumes returned in the response is truncated, the response includes a marker field. You can use this marker value in your subsequent request to retrieve the next set of volumes. This operation is only supported in the cached volume and stored volume gateway architectures.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/ListVolumes>`_


``list-volumes`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``VolumeInfos``


========
Synopsis
========

::

    list-volumes
  [--gateway-arn <value>]
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



========
Examples
========

**To list the volumes configured for a gateway**

The following ``list-volumes`` command returns a list of volumes configured for the specified gateway.
To specify which gateway to describe, use the Amazon Resource Name (ARN) of the gateway in the command.

This examples specifies a gateway with the id ``sgw-12A3456B`` in account ``123456789012``::

    aws storagegateway list-volumes --gateway-arn "arn:aws:storagegateway:us-west-2:123456789012:gateway/sgw-12A3456B"

This command outputs a JSON block that a list of volumes that includes the type and ARN for each volume.


======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

Marker -> (string)

  

  

VolumeInfos -> (list)

  

  (structure)

    

    Describes a storage volume object.

    

    VolumeARN -> (string)

      

      The Amazon Resource Name (ARN) for the storage volume. For example, the following is a valid ARN:

       

       ``arn:aws:storagegateway:us-east-1:111122223333:gateway/sgw-12A3456B/volume/vol-1122AABB``  

       

      Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

      

      

    VolumeId -> (string)

      

      The unique identifier assigned to the volume. This ID becomes part of the volume Amazon Resource Name (ARN), which you use as input for other operations.

       

      Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

      

      

    GatewayARN -> (string)

      

      The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

      

      

    GatewayId -> (string)

      

      The unique identifier assigned to your gateway during activation. This ID becomes part of the gateway Amazon Resource Name (ARN), which you use as input for other operations.

       

      Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

      

      

    VolumeType -> (string)

      

      

    VolumeSizeInBytes -> (long)

      

      The size of the volume in bytes.

       

      Valid Values: 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

      

      

    

  

