[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr complete-layer-upload:


*********************
complete-layer-upload
*********************



===========
Description
===========



Inform Amazon ECR that the image layer upload for a specified registry, repository name, and upload ID, has completed. You can optionally provide a ``sha256`` digest of the image layer for data validation purposes.

 

.. note::

   

  This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers for pulling and pushing images. In most cases, you should use the ``docker`` CLI to pull, tag, and push images.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/CompleteLayerUpload>`_


========
Synopsis
========

::

    complete-layer-upload
  [--registry-id <value>]
  --repository-name <value>
  --upload-id <value>
  --layer-digests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry to which to upload layers. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository to associate with the image layer.

  

``--upload-id`` (string)


  The upload ID from a previous  initiate-layer-upload operation to associate with the image layer.

  

``--layer-digests`` (list)


  The ``sha256`` digest of the image layer.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

registryId -> (string)

  

  The registry ID associated with the request.

  

  

repositoryName -> (string)

  

  The repository name associated with the request.

  

  

uploadId -> (string)

  

  The upload ID associated with the layer.

  

  

layerDigest -> (string)

  

  The ``sha256`` digest of the image layer.

  

  

