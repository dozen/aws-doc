[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway add-working-storage:


*******************
add-working-storage
*******************



===========
Description
===========



Configures one or more gateway local disks as working storage for a gateway. This operation is only supported in the stored volume gateway architecture. This operation is deprecated in cached volume API version 20120630. Use  add-upload-buffer instead.

 

.. note::

   

  Working storage is also referred to as upload buffer. You can also use the  add-upload-buffer operation to add upload buffer to a stored volume gateway.

   

 

In the request, you specify the gateway Amazon Resource Name (ARN) to which you want to add working storage, and one or more disk IDs that you want to configure as working storage.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/AddWorkingStorage>`_


========
Synopsis
========

::

    add-working-storage
  --gateway-arn <value>
  --disk-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--disk-ids`` (list)


  An array of strings that identify disks that are to be configured as working storage. Each string have a minimum length of 1 and maximum length of 300. You can get the disk IDs from the  list-local-disks API.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

