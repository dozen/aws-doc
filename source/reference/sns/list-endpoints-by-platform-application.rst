[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns list-endpoints-by-platform-application:


**************************************
list-endpoints-by-platform-application
**************************************



===========
Description
===========



Lists the endpoints and endpoint attributes for devices in a supported push notification service, such as GCM and APNS. The results for ``list-endpoints-by-platform-application`` are paginated and return a limited list of endpoints, up to 100. If additional records are available after the first page results, then a NextToken string will be returned. To receive the next page, you call ``list-endpoints-by-platform-application`` again using the NextToken string received from the previous call. When there are no more records to return, NextToken will be null. For more information, see `Using Amazon SNS Mobile Push Notifications`_ . 



``list-endpoints-by-platform-application`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Endpoints``


========
Synopsis
========

::

    list-endpoints-by-platform-application
  --platform-application-arn <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--platform-application-arn`` (string)


  PlatformApplicationArn for ListEndpointsByPlatformApplicationInput action.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Endpoints -> (list)

  

  Endpoints returned for list-endpoints-by-platform-application action.

  

  (structure)

    

    Endpoint for mobile app and device.

    

    EndpointArn -> (string)

      

      EndpointArn for mobile app and device.

      

      

    Attributes -> (map)

      

      Attributes for endpoint.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

NextToken -> (string)

  

  NextToken string is returned when calling list-endpoints-by-platform-application action if additional records are available after the first page results.

  

  



.. _Using Amazon SNS Mobile Push Notifications: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html
