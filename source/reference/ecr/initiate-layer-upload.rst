[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr initiate-layer-upload:


*********************
initiate-layer-upload
*********************



===========
Description
===========



Notify Amazon ECR that you intend to upload an image layer. 

 

.. note::

   

  This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

   



========
Synopsis
========

::

    initiate-layer-upload
  [--registry-id <value>]
  --repository-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that you intend to upload layers to. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository that you intend to upload layers to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

uploadId -> (string)

  

  The upload ID for the layer upload. This parameter is passed to further  upload-layer-part and  complete-layer-upload operations.

  

  

partSize -> (long)

  

  The size, in bytes, that Amazon ECR expects future layer part uploads to be.

  

  

