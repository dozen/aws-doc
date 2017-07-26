[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-client-certificates:


***********************
get-client-certificates
***********************



===========
Description
===========



Gets a collection of  ClientCertificate resources.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetClientCertificates>`_


``get-client-certificates`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``items``


========
Synopsis
========

::

    get-client-certificates
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get a list of client certificates**

Command::

  aws apigateway get-client-certificates

Output::

  {
      "items": [
          {
              "pemEncodedCertificate": "-----BEGIN CERTIFICATE----- <certificate content> -----END CERTIFICATE-----", 
              "clientCertificateId": "a1b2c3", 
              "expirationDate": 1483556561, 
              "description": "My Client Certificate", 
              "createdDate": 1452020561
          }
      ]
  }



======
Output
======

position -> (string)

  

  

items -> (list)

  

  The current page of elements from this collection.

  

  (structure)

    

    Represents a client certificate used to configure client-side SSL authentication while sending requests to the integration endpoint.

     Client certificates are used authenticate an API by the back-end server. To authenticate an API client (or user), use a custom  Authorizer .  `Use Client-Side Certificate <http://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started-client-side-ssl-authentication.html>`_  

    clientCertificateId -> (string)

      

      The identifier of the client certificate.

      

      

    description -> (string)

      

      The description of the client certificate.

      

      

    pemEncodedCertificate -> (string)

      

      The PEM-encoded public key of the client certificate, which can be used to configure certificate authentication in the integration endpoint .

      

      

    createdDate -> (timestamp)

      

      The timestamp when the client certificate was created.

      

      

    expirationDate -> (timestamp)

      

      The timestamp when the client certificate will expire.

      

      

    

  

