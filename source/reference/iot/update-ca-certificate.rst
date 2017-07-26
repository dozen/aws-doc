[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot update-ca-certificate:


*********************
update-ca-certificate
*********************



===========
Description
===========



Updates a registered CA certificate.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/UpdateCACertificate>`_


========
Synopsis
========

::

    update-ca-certificate
  --certificate-id <value>
  [--new-status <value>]
  [--new-auto-registration-status <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-id`` (string)


  The CA certificate identifier.

  

``--new-status`` (string)


  The updated status of the CA certificate.

   

   **Note:** The status value REGISTER_INACTIVE is deprecated and should not be used.

  

  Possible values:

  
  *   ``ACTIVE``

  
  *   ``INACTIVE``

  

  

``--new-auto-registration-status`` (string)


  The new value for the auto registration status. Valid values are: "ENABLE" or "DISABLE".

  

  Possible values:

  
  *   ``ENABLE``

  
  *   ``DISABLE``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None