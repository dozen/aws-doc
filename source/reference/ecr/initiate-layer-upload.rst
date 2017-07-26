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

   

  This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers for pulling and pushing images. In most cases, you should use the ``docker`` CLI to pull, tag, and push images.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/InitiateLayerUpload>`_


========
Synopsis
========

::

    initiate-layer-upload
  [--registry-id <value>]
  --repository-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that you intend to upload layers to. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository that you intend to upload layers to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

uploadId -> (string)

  

  The upload ID for the layer upload. This parameter is passed to further  upload-layer-part and  complete-layer-upload operations.

  

  

partSize -> (long)

  

  The size, in bytes, that Amazon ECR expects future layer part uploads to be.

  

  

