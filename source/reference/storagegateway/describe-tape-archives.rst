[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-tape-archives:


**********************
describe-tape-archives
**********************



===========
Description
===========



Returns a description of specified virtual tapes in the virtual tape shelf (VTS). This operation is only supported in the tape gateway architecture.

 

If a specific ``TapeARN`` is not specified, AWS Storage Gateway returns a description of all virtual tapes found in the VTS associated with your account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DescribeTapeArchives>`_


``describe-tape-archives`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``TapeArchives``


========
Synopsis
========

::

    describe-tape-archives
  [--tape-arns <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--tape-arns`` (list)


  Specifies one or more unique Amazon Resource Names (ARNs) that represent the virtual tapes you want to describe.

  



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

TapeArchives -> (list)

  

  An array of virtual tape objects in the virtual tape shelf (VTS). The description includes of the Amazon Resource Name(ARN) of the virtual tapes. The information returned includes the Amazon Resource Names (ARNs) of the tapes, size of the tapes, status of the tapes, progress of the description and tape barcode.

  

  (structure)

    

    Represents a virtual tape that is archived in the virtual tape shelf (VTS).

    

    TapeARN -> (string)

      

      The Amazon Resource Name (ARN) of an archived virtual tape.

      

      

    TapeBarcode -> (string)

      

      The barcode that identifies the archived virtual tape.

      

      

    TapeCreatedDate -> (timestamp)

      

      

    TapeSizeInBytes -> (long)

      

      The size, in bytes, of the archived virtual tape.

      

      

    CompletionTime -> (timestamp)

      

      The time that the archiving of the virtual tape was completed.

       

      The string format of the completion time is in the ISO8601 extended YYYY-MM-DD'T'HH:MM:SS'Z' format.

      

      

    RetrievedTo -> (string)

      

      The Amazon Resource Name (ARN) of the tape gateway that the virtual tape is being retrieved to.

       

      The virtual tape is retrieved from the virtual tape shelf (VTS).

      

      

    TapeStatus -> (string)

      

      The current state of the archived virtual tape.

      

      

    TapeUsedInBytes -> (long)

      

      The size, in bytes, of data written to the virtual tape.

       

      .. note::

         

        This value is not available for tapes created prior to May,13 2015.

         

      

      

    

  

Marker -> (string)

  

  An opaque string that indicates the position at which the virtual tapes that were fetched for description ended. Use this marker in your next request to fetch the next set of virtual tapes in the virtual tape shelf (VTS). If there are no more virtual tapes to describe, this field does not appear in the response.

  

  

