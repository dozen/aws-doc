[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog delete-provisioning-artifact:


****************************
delete-provisioning-artifact
****************************



===========
Description
===========



Deletes the specified provisioning artifact. This operation does not work on a provisioning artifact associated with a product that has been shared with you, or on the last provisioning artifact associated with a product (a product must have at least one provisioning artifact).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/DeleteProvisioningArtifact>`_


========
Synopsis
========

::

    delete-provisioning-artifact
  [--accept-language <value>]
  --product-id <value>
  --provisioning-artifact-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--accept-language`` (string)


  The language code to use for this operation. Supported language codes are as follows:

   

  "en" (English)

   

  "jp" (Japanese)

   

  "zh" (Chinese)

   

  If no code is specified, "en" is used as the default.

  

``--product-id`` (string)


  The product identifier.

  

``--provisioning-artifact-id`` (string)


  The identifier of the provisioning artifact for the delete request. This is sometimes referred to as the product version.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

