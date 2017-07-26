[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway list-file-shares:


****************
list-file-shares
****************



===========
Description
===========



Gets a list of the file shares for a specific file gateway, or the list of file shares that belong to the calling user account. This operation is only supported in the file gateway architecture.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/ListFileShares>`_


========
Synopsis
========

::

    list-file-shares
  [--gateway-arn <value>]
  [--limit <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon resource Name (ARN) of the gateway whose file shares you want to list. If this field is not present, all file shares under your account are listed.

  

``--limit`` (integer)


  The maximum number of file shares to return in the response. The value must be an integer with a value greater than zero. Optional.

  

``--marker`` (string)


  Opaque pagination token returned from a previous list-file-shares operation. If present, ``marker`` specifies where to continue the list from after a previous call to ListFileShares. Optional.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  If the request includes ``marker`` , the response returns that value in this field. 

  

  

NextMarker -> (string)

  

  If a value is present, there are more file shares to return. In a subsequent request, use ``NextMarker`` as the value for ``marker`` to retrieve the next set of file shares. 

  

  

FileShareInfoList -> (list)

  

  An array of information about the file gateway's file shares. 

  

  (structure)

    

    Describes a file share.

    

    FileShareARN -> (string)

      

      The Amazon Resource Name (ARN) of the file share. 

      

      

    FileShareId -> (string)

      

      The ID of the file share. 

      

      

    FileShareStatus -> (string)

      

      The status of the file share. Possible values are CREATING, UPDATING, AVAILABLE and DELETING. 

      

      

    GatewayARN -> (string)

      

      The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

      

      

    

  

