[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-tapes:


**************
describe-tapes
**************



===========
Description
===========



Returns a description of the specified Amazon Resource Name (ARN) of virtual tapes. If a ``TapeARN`` is not specified, returns a description of all virtual tapes associated with the specified gateway.



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
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--tape-arns`` (list)


  Specifies one or more unique Amazon Resource Names (ARNs) that represent the virtual tapes you want to describe. If this parameter is not specified, AWS Storage Gateway returns a description of all virtual tapes associated with the specified gateway.

  



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

Tapes -> (list)

  

  An array of virtual tape descriptions.

  

  (structure)

    

    Describes a virtual tape object.

    

    TapeARN -> (string)

      

      The Amazon Resource Name (ARN) of the virtual tape.

      

      

    TapeBarcode -> (string)

      

      The barcode that identifies a specific virtual tape.

      

      

    TapeSizeInBytes -> (long)

      

      The size, in bytes, of the virtual tape.

      

      

    TapeStatus -> (string)

      

      The current state of the virtual tape. 

      

      

    VTLDevice -> (string)

      

      The virtual tape library (VTL) device that the virtual tape is associated with.

      

      

    Progress -> (double)

      

      For archiving virtual tapes, indicates how much data remains to be uploaded before archiving is complete.

       

      Range: 0 (not started) to 100 (complete).

      

      

    

  

Marker -> (string)

  

  An opaque string which can be used as part of a subsequent describe-tapes call to retrieve the next page of results. 

   

  If a response does not contain a marker, then there are no more results to be retrieved.

  

  

