[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns list-platform-applications:


**************************
list-platform-applications
**************************



===========
Description
===========



Lists the platform application objects for the supported push notification services, such as APNS and GCM. The results for ``list-platform-applications`` are paginated and return a limited list of applications, up to 100. If additional records are available after the first page results, then a NextToken string will be returned. To receive the next page, you call ``list-platform-applications`` using the NextToken string received from the previous call. When there are no more records to return, NextToken will be null. For more information, see `Using Amazon SNS Mobile Push Notifications <http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/ListPlatformApplications>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

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

  

  

