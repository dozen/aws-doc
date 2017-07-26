[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway add-cache:


*********
add-cache
*********



===========
Description
===========



Configures one or more gateway local disks as cache for a gateway. This operation is only supported in the cached volume, tape and file gateway architectures (see `Storage Gateway Concepts <http://docs.aws.amazon.com/storagegateway/latest/userguide/StorageGatewayConcepts.html>`_ ).

 

In the request, you specify the gateway Amazon Resource Name (ARN) to which you want to add cache, and one or more disk IDs that you want to configure as cache.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/AddCache>`_


========
Synopsis
========

::

    add-cache
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

  

  

