[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-tapes:


**************
describe-tapes
**************



===========
Description
===========



Returns a description of the specified Amazon Resource Name (ARN) of virtual tapes. If a ``TapeARN`` is not specified, returns a description of all virtual tapes associated with the specified gateway. This operation is only supported in the tape gateway architecture.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DescribeTapes>`_


``describe-tapes`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Tapes``


========
Synopsis
========

::

    describe-tapes
  --gateway-arn <value>
  [--tape-arns <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--tape-arns`` (list)


  Specifies one or more unique Amazon Resource Names (ARNs) that represent the virtual tapes you want to describe. If this parameter is not specified, Tape gateway returns a description of all virtual tapes associated with the specified gateway.

  



Syntax::

  "string" "string" ...



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



======
Output
======

Tapes -> (list)

  

  An array of virtual tape descriptions.

  

  (structure)

    

    Describes a virtual tape object.

    

    TapeARN -> (string)

      

      The Amazon Resource Name (ARN) of the virtual tape.

      

      

    TapeBarcode -> (string)

      

      The barcode that identifies a specific virtual tape.

      

      

    TapeCreatedDate -> (timestamp)

      

      The date the virtual tape was created.

      

      

    TapeSizeInBytes -> (long)

      

      The size, in bytes, of the virtual tape capacity.

      

      

    TapeStatus -> (string)

      

      The current state of the virtual tape.

      

      

    VTLDevice -> (string)

      

      The virtual tape library (VTL) device that the virtual tape is associated with.

      

      

    Progress -> (double)

      

      For archiving virtual tapes, indicates how much data remains to be uploaded before archiving is complete.

       

      Range: 0 (not started) to 100 (complete).

      

      

    TapeUsedInBytes -> (long)

      

      The size, in bytes, of data written to the virtual tape.

       

      .. note::

         

        This value is not available for tapes created prior to May,13 2015.

         

      

      

    

  

Marker -> (string)

  

  An opaque string which can be used as part of a subsequent describe-tapes call to retrieve the next page of results.

   

  If a response does not contain a marker, then there are no more results to be retrieved.

  

  

