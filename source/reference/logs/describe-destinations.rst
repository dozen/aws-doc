[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs describe-destinations:


*********************
describe-destinations
*********************



===========
Description
===========



Returns all the destinations that are associated with the AWS account making the request. The list returned in the response is ASCII-sorted by destination name. 

 

By default, this operation returns up to 50 destinations. If there are more destinations to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of destinations returned in the response by specifying the ``limit`` parameter in the request. 



``describe-destinations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``destinations``


========
Synopsis
========

::

    describe-destinations
  [--destination-name-prefix <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--destination-name-prefix`` (string)


  Will only return destinations that match the provided destinationNamePrefix. If you don't specify a value, no prefix is applied.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

destinations -> (list)

  

  (structure)

    

    A cross account destination that is the recipient of subscription log events.

    

    destinationName -> (string)

      

      Name of the destination.

      

      

    targetArn -> (string)

      

      ARN of the physical target where the log events will be delivered (eg. ARN of a Kinesis stream).

      

      

    roleArn -> (string)

      

      A role for impersonation for delivering log events to the target.

      

      

    accessPolicy -> (string)

      

      An IAM policy document that governs which AWS accounts can create subscription filters against this destination.

      

      

    arn -> (string)

      

      ARN of this destination.

      

      

    creationTime -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC specifying when this destination was created.

      

      

    

  

nextToken -> (string)

  

  A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

  

  

