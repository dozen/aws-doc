[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns list-platform-applications:


**************************
list-platform-applications
**************************



===========
Description
===========



Lists the platform application objects for the supported push notification services, such as APNS and GCM. The results for ``list-platform-applications`` are paginated and return a limited list of applications, up to 100. If additional records are available after the first page results, then a NextToken string will be returned. To receive the next page, you call ``list-platform-applications`` using the NextToken string received from the previous call. When there are no more records to return, NextToken will be null. For more information, see `Using Amazon SNS Mobile Push Notifications`_ . 



``list-platform-applications`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``PlatformApplications``


========
Synopsis
========

::

    list-platform-applications
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

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

PlatformApplications -> (list)

  

  Platform applications returned when calling list-platform-applications action.

  

  (structure)

    

    Platform application object.

    

    PlatformApplicationArn -> (string)

      

      PlatformApplicationArn for platform application object.

      

      

    Attributes -> (map)

      

      Attributes for platform application object.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

NextToken -> (string)

  

  NextToken string is returned when calling list-platform-applications action if additional records are available after the first page results.

  

  



.. _Using Amazon SNS Mobile Push Notifications: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html
