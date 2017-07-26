[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr batch-check-layer-availability:


******************************
batch-check-layer-availability
******************************



===========
Description
===========



Check the availability of multiple image layers in a specified registry and repository.

 

.. note::

   

  This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers for pulling and pushing images. In most cases, you should use the ``docker`` CLI to pull, tag, and push images.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/BatchCheckLayerAvailability>`_


========
Synopsis
========

::

    batch-check-layer-availability
  [--registry-id <value>]
  --repository-name <value>
  --layer-digests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the image layers to check. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository that is associated with the image layers to check.

  

``--layer-digests`` (list)


  The digests of the image layers to check.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

layers -> (list)

  

  A list of image layer objects corresponding to the image layer references in the request.

  

  (structure)

    

    An object representing an Amazon ECR image layer.

    

    layerDigest -> (string)

      

      The ``sha256`` digest of the image layer.

      

      

    layerAvailability -> (string)

      

      The availability status of the image layer.

      

      

    layerSize -> (long)

      

      The size, in bytes, of the image layer.

      

      

    mediaType -> (string)

      

      The media type of the layer, such as ``application/vnd.docker.image.rootfs.diff.tar.gzip`` or ``application/vnd.oci.image.layer.v1.tar+gzip`` .

      

      

    

  

failures -> (list)

  

  Any failures associated with the call.

  

  (structure)

    

    An object representing an Amazon ECR image layer failure.

    

    layerDigest -> (string)

      

      The layer digest associated with the failure.

      

      

    failureCode -> (string)

      

      The failure code associated with the failure.

      

      

    failureReason -> (string)

      

      The reason for the failure.

      

      

    

  

