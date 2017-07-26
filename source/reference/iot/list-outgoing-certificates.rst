[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-outgoing-certificates:


**************************
list-outgoing-certificates
**************************



===========
Description
===========



Lists certificates that are being transfered but not yet accepted.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/ListOutgoingCertificates>`_


``list-outgoing-certificates`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``outgoingCertificates``


========
Synopsis
========

::

    list-outgoing-certificates
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


  Specifies the order for results. If True, the results are returned in ascending order, based on the creation date.

  

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

outgoingCertificates -> (list)

  

  The certificates that are being transfered but not yet accepted.

  

  (structure)

    

    A certificate that has been transfered but not yet accepted.

    

    certificateArn -> (string)

      

      The certificate ARN.

      

      

    certificateId -> (string)

      

      The certificate ID.

      

      

    transferredTo -> (string)

      

      The AWS account to which the transfer was made.

      

      

    transferDate -> (timestamp)

      

      The date the transfer was initiated.

      

      

    transferMessage -> (string)

      

      The transfer message.

      

      

    creationDate -> (timestamp)

      

      The certificate creation date.

      

      

    

  

nextMarker -> (string)

  

  The marker for the next set of results.

  

  

