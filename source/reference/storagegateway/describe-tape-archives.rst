[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-tape-archives:


**********************
describe-tape-archives
**********************



===========
Description
===========



Returns a description of specified virtual tapes in the virtual tape shelf (VTS). 

 

If a specific ``TapeARN`` is not specified, AWS Storage Gateway returns a description of all virtual tapes found in the VTS associated with your account.



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
  [--generate-cli-skeleton]




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

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      

    TapeSizeInBytes -> (long)

      

      The size, in bytes, of the archived virtual tape.

      

      

    CompletionTime -> (timestamp)

      

      The time that the archiving of the virtual tape was completed.

       

      The string format of the completion time is in the ISO8601 extended YYYY-MM-DD'T'HH:MM:SS'Z' format.

      

      

    RetrievedTo -> (string)

      

      The Amazon Resource Name (ARN) of the gateway-VTL that the virtual tape is being retrieved to. 

       

      The virtual tape is retrieved from the virtual tape shelf (VTS).

      

      

    TapeStatus -> (string)

      

      The current state of the archived virtual tape. 

      

      

    

  

Marker -> (string)

  

  An opaque string that indicates the position at which the virtual tapes that were fetched for description ended. Use this marker in your next request to fetch the next set of virtual tapes in the virtual tape shelf (VTS). If there are no more virtual tapes to describe, this field does not appear in the response. 

  

  

