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

   

  This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

   



========
Synopsis
========

::

    batch-check-layer-availability
  [--registry-id <value>]
  --repository-name <value>
  --layer-digests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

layers -> (list)

  

  A list of image layer objects corresponding to the image layer references in the request.

  

  (structure)

    

    layerDigest -> (string)

      

      The ``sha256`` digest of the image layer.

      

      

    layerAvailability -> (string)

      

      The availability status of the image layer. Valid values are ``AVAILABLE`` and ``UNAVAILABLE`` .

      

      

    layerSize -> (long)

      

      The size, in bytes, of the image layer.

      

      

    

  

failures -> (list)

  

  Any failures associated with the call.

  

  (structure)

    

    layerDigest -> (string)

      

      The layer digest associated with the failure.

      

      

    failureCode -> (string)

      

      The failure code associated with the failure.

      

      

    failureReason -> (string)

      

      The reason for the failure.

      

      

    

  

