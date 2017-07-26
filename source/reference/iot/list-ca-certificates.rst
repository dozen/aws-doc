[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-ca-certificates:


********************
list-ca-certificates
********************



===========
Description
===========



Lists the CA certificates registered for your AWS account.

 

The results are paginated with a default page size of 25. You can use the returned marker to retrieve additional results.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/ListCACertificates>`_


``list-ca-certificates`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``certificates``


========
Synopsis
========

::

    list-ca-certificates
  [--page-size <value>]
  [--ascending-order | --no-ascending-order]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--ascending-order`` | ``--no-ascending-order`` (boolean)


  Determines the order of the results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

certificates -> (list)

  

  The CA certificates registered in your AWS account.

  

  (structure)

    

    A CA certificate.

    

    certificateArn -> (string)

      

      The ARN of the CA certificate.

      

      

    certificateId -> (string)

      

      The ID of the CA certificate.

      

      

    status -> (string)

      

      The status of the CA certificate.

       

      The status value REGISTER_INACTIVE is deprecated and should not be used.

      

      

    creationDate -> (timestamp)

      

      The date the CA certificate was created.

      

      

    

  

nextMarker -> (string)

  

  The current position within the list of CA certificates.

  

  

