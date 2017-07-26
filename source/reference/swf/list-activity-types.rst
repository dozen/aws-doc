[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf list-activity-types:


*******************
list-activity-types
*******************



===========
Description
===========



Returns information about all activities registered in the specified domain that match the specified name and registration status. The result includes information like creation date, current status of the activity, etc. The results may be split into multiple pages. To retrieve subsequent pages, make the call again using the ``nextPageToken`` returned by the initial call.

 

 **Access Control**  

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains. 
 
* Use an ``Action`` element to allow or deny permission to call this action. 
 
* You cannot use an IAM policy to constrain this action's parameters. 
 

 

If the caller doesn't have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's ``cause`` parameter is set to ``OPERATION_NOT_PERMITTED`` . For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows <http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html>`_ in the *Amazon SWF Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/swf-2012-01-25/ListActivityTypes>`_


``list-activity-types`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``typeInfos``


========
Synopsis
========

::

    list-activity-types
  --domain <value>
  [--name <value>]
  --registration-status <value>
  [--reverse-order | --no-reverse-order]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain`` (string)


  The name of the domain in which the activity types have been registered.

  

``--name`` (string)


  If specified, only lists the activity types that have this name.

  

``--registration-status`` (string)


  Specifies the registration status of the activity types to list.

  

  Possible values:

  
  *   ``REGISTERED``

  
  *   ``DEPRECATED``

  

  

``--reverse-order`` | ``--no-reverse-order`` (boolean)


  When set to ``true`` , returns the results in reverse order. By default, the results are returned in ascending alphabetical order by ``name`` of the activity types.

  

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



========
Examples
========

Listing Activity Types
----------------------

To get a list of the activity types for a domain, use ``swf list-activity-types``. The ``--domain`` and
``--registration-status`` arguments are required. Here's a simple example::

    aws swf list-activity-types --domain DataFrobtzz --registration-status REGISTERED

Results::

    {
        "typeInfos": [
            {
                "status": "REGISTERED",
                "creationDate": 1371454150.451,
                "activityType": {
                    "version": "1",
                    "name": "confirm-user-email"
                },
                "description": "subscribe confirm-user-email activity"
            },
            {
                "status": "REGISTERED",
                "creationDate": 1371454150.709,
                "activityType": {
                    "version": "1",
                    "name": "confirm-user-phone"
                },
                "description": "subscribe confirm-user-phone activity"
            },
            {
                "status": "REGISTERED",
                "creationDate": 1371454149.871,
                "activityType": {
                    "version": "1",
                    "name": "get-subscription-info"
                },
                "description": "subscribe get-subscription-info activity"
            },
            {
                "status": "REGISTERED",
                "creationDate": 1371454150.909,
                "activityType": {
                    "version": "1",
                    "name": "send-subscription-success"
                },
                "description": "subscribe send-subscription-success activity"
            },
            {
                "status": "REGISTERED",
                "creationDate": 1371454150.085,
                "activityType": {
                    "version": "1",
                    "name": "subscribe-user-sns"
                },
                "description": "subscribe subscribe-user-sns activity"
            }
        ]
    }

You can use the ``--name`` argument to select only activity types with a particular name::

    aws swf list-activity-types --domain DataFrobtzz --registration-status REGISTERED --name "send-subscription-success"

Results::

    {
        "typeInfos": [
            {
                "status": "REGISTERED",
                "creationDate": 1371454150.909,
                "activityType": {
                    "version": "1",
                    "name": "send-subscription-success"
                },
                "description": "subscribe send-subscription-success activity"
            }
        ]
    }

To retrieve results in pages, you can set the ``--maximum-page-size`` argument. If more results are returned than will
fit in a page of results, a "nextPageToken" will be returned in the result set::

    aws swf list-activity-types --domain DataFrobtzz --registration-status REGISTERED --maximum-page-size 2

Results::

    {
        "nextPageToken": "AAAAKgAAAAEAAAAAAAAAA1Gp1BelJq+PmHvAnDxJYbup8+0R4LVtbXLDl7QNY7C3OpHo9Sz06D/GuFz1OyC73umBQ1tOPJ/gC/aYpzDMqUIWIA1T9W0s2DryyZX4OC/6Lhk9/o5kdsuWMSBkHhgaZjgwp3WJINIFJFdaSMxY2vYAX7AtRtpcqJuBDDRE9RaRqDGYqIYUMltarkiqpSY1ZVveBasBvlvyUb/WGAaqehiDz7/JzLT/wWNNUMOd+Nhe",
        "typeInfos": [
            {
                "status": "REGISTERED",
                "creationDate": 1371454150.451,
                "activityType": {
                    "version": "1",
                    "name": "confirm-user-email"
                },
                "description": "subscribe confirm-user-email activity"
            },
            {
                "status": "REGISTERED",
                "creationDate": 1371454150.709,
                "activityType": {
                    "version": "1",
                    "name": "confirm-user-phone"
                },
                "description": "subscribe confirm-user-phone activity"
            }
        ]
    }

You can pass the nextPageToken value to the next call to ``list-activity-types`` in the ``--next-page-token`` argument,
retrieving the next page of results::

    aws swf list-activity-types --domain DataFrobtzz --registration-status REGISTERED --maximum-page-size 2
    --next-page-token "AAAAKgAAAAEAAAAAAAAAA1Gp1BelJq+PmHvAnDxJYbup8+0R4LVtbXLDl7QNY7C3OpHo9Sz06D/GuFz1OyC73umBQ1tOPJ/gC/aYpzDMqUIWIA1T9W0s2DryyZX4OC/6Lhk9/o5kdsuWMSBkHhgaZjgwp3WJINIFJFdaSMxY2vYAX7AtRtpcqJuBDDRE9RaRqDGYqIYUMltarkiqpSY1ZVveBasBvlvyUb/WGAaqehiDz7/JzLT/wWNNUMOd+Nhe"

Result::

    {
        "nextPageToken": "AAAAKgAAAAEAAAAAAAAAAw+7LZ4GRZPzTqBHsp2wBxWB8m1sgLCclgCuq3J+h/m3+vOfFqtkcjLwV5cc4OjNAzTCuq/XcylPumGwkjbajtqpZpbqOcVNfjFxGoi0LB2Olbvv0krbUISBvlpFPmSWpDSZJsxg5UxCcweteSlFn1PNSZ/MoinBZo8OTkjMuzcsTuKOzH9wCaR8ITcALJ3SaqHU3pyIRS5hPmFA3OLIc8zaAepjlaujo6hntNSCruB4"
        "typeInfos": [
            {
                "status": "REGISTERED",
                "creationDate": 1371454149.871,
                "activityType": {
                    "version": "1",
                    "name": "get-subscription-info"
                },
                "description": "subscribe get-subscription-info activity"
            },
            {
                "status": "REGISTERED",
                "creationDate": 1371454150.909,
                "activityType": {
                    "version": "1",
                    "name": "send-subscription-success"
                },
                "description": "subscribe send-subscription-success activity"
            }
        ]
    }

If there are still more results to return, "nextPageToken" will be returned with the results. When there are no more
pages of results to return, "nextPageToken" will *not* be returned in the result set.

You can use the ``--reverse-order`` argument to reverse the order of the returned results. This also affects paged
results::

    aws swf list-activity-types --domain DataFrobtzz --registration-status REGISTERED --maximum-page-size 2 --reverse-order

Results::

    {
        "nextPageToken": "AAAAKgAAAAEAAAAAAAAAAwXcpu5ePSyQkrC+8WMbmSrenuZC2ZkIXQYBPB/b9xIOVkj+bMEFhGj0KmmJ4rF7iddhjf7UMYCsfGkEn7mk+yMCgVc1JxDWmB0EH46bhcmcLmYNQihMDmUWocpr7To6/R7CLu0St1gkFayxOidJXErQW0zdNfQaIWAnF/cwioBbXlkz1fQzmDeU3M5oYGMPQIrUqkPq7pMEW0q0lK5eDN97NzFYdZZ/rlcLDWPZhUjY",
        "typeInfos": [
            {
                "status": "REGISTERED",
                "creationDate": 1371454150.085,
                "activityType": {
                    "version": "1",
                    "name": "subscribe-user-sns"
                },
                "description": "subscribe subscribe-user-sns activity"
            },
            {
                "status": "REGISTERED",
                "creationDate": 1371454150.909,
                "activityType": {
                    "version": "1",
                    "name": "send-subscription-success"
                },
                "description": "subscribe send-subscription-success activity"
            }
        ]
    }

See Also
--------

-  `ListActivityTypes <http://docs.aws.amazon.com/amazonswf/latest/apireference/API_ListActivityTypes.html>`_
   in the *Amazon Simple Workflow Service API Reference*



======
Output
======

typeInfos -> (list)

  

  List of activity type information.

  

  (structure)

    

    Detailed information about an activity type.

    

    activityType -> (structure)

      

      The  ActivityType type structure representing the activity type.

      

      name -> (string)

        

        The name of this activity.

         

        .. note::

           

          The combination of activity type name and version must be unique within a domain.

           

        

        

      version -> (string)

        

        The version of this activity.

         

        .. note::

           

          The combination of activity type name and version must be unique with in a domain.

           

        

        

      

    status -> (string)

      

      The current status of the activity type.

      

      

    description -> (string)

      

      The description of the activity type provided in  register-activity-type .

      

      

    creationDate -> (timestamp)

      

      The date and time this activity type was created through  register-activity-type .

      

      

    deprecationDate -> (timestamp)

      

      If DEPRECATED, the date and time  deprecate-activity-type was called.

      

      

    

  

nextPageToken -> (string)

  

  If a ``NextPageToken`` was returned by a previous call, there are more results available. To retrieve the next page of results, make the call again using the returned token in ``nextPageToken`` . Keep all other arguments unchanged.

   

  The configured ``maximumPageSize`` determines how many results can be returned in a single call.

  

  

