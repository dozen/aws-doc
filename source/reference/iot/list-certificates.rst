[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-certificates:


*****************
list-certificates
*****************



===========
Description
===========



Lists your certificates.

 

The results are paginated with a default page size of 25. You can retrieve additional results using the returned marker.



========
Synopsis
========

::

    list-certificates
  [--page-size <value>]
  [--marker <value>]
  [--ascending-order | --no-ascending-order]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--page-size`` (integer)


  The result page size.

  

``--marker`` (string)


  The marker for the next set of results.

  

``--ascending-order`` | ``--no-ascending-order`` (boolean)


  Specifies the order for results. If True, the results are returned in ascending order, based on the creation date.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

certificates -> (list)

  

  The descriptions of the certificates.

  

  (structure)

    

    Information about a certificate.

    

    certificateArn -> (string)

      

      The ARN of the certificate.

      

      

    certificateId -> (string)

      

      The ID of the certificate.

      

      

    status -> (string)

      

      The status of the certificate.

      

      

    creationDate -> (timestamp)

      

      The date and time the certificate was created.

      

      

    

  

nextMarker -> (string)

  

  The marker for the next set of results, or null if there are no additional results.

  

  

