[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs describe-users:


**************
describe-users
**************



===========
Description
===========



Describes the specified users. You can describe all users or filter the results (for example, by status or organization).

 

By default, Amazon WorkDocs returns the first 24 active or pending users. If there are more results, the response includes a marker that you can use to request the next set of results.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/DescribeUsers>`_


``describe-users`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Users``


========
Synopsis
========

::

    describe-users
  [--authentication-token <value>]
  [--organization-id <value>]
  [--user-ids <value>]
  [--include <value>]
  [--order <value>]
  [--sort <value>]
  [--fields <value>]
  [--user-query <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--organization-id`` (string)


  The ID of the organization.

  

``--user-ids`` (string)


  The IDs of the users.

  

``--include`` (string)


  The state of the users. Specify "ALL" to include inactive users.

  

  Possible values:

  
  *   ``ALL``

  
  *   ``ACTIVE_PENDING``

  

  

``--order`` (string)


  The order for the results.

  

  Possible values:

  
  *   ``ASCENDING``

  
  *   ``DESCENDING``

  

  

``--sort`` (string)


  The sorting criteria.

  

  Possible values:

  
  *   ``USER_NAME``

  
  *   ``FULL_NAME``

  
  *   ``STORAGE_LIMIT``

  
  *   ``USER_STATUS``

  
  *   ``STORAGE_USED``

  

  

``--fields`` (string)


  A comma-separated list of values. Specify "STORAGE_METADATA" to include the user storage quota and utilization information.

  

``--user-query`` (string)


  A query to filter users by user name.

  

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

Users -> (list)

  

  The users.

  

  (structure)

    

    Describes a user.

    

    Id -> (string)

      

      The ID of the user.

      

      

    Username -> (string)

      

      The login name of the user.

      

      

    EmailAddress -> (string)

      

      The email address of the user.

      

      

    GivenName -> (string)

      

      The given name of the user.

      

      

    Surname -> (string)

      

      The surname of the user.

      

      

    OrganizationId -> (string)

      

      The ID of the organization.

      

      

    RootFolderId -> (string)

      

      The ID of the root folder.

      

      

    RecycleBinFolderId -> (string)

      

      The ID of the recycle bin folder.

      

      

    Status -> (string)

      

      The status of the user.

      

      

    Type -> (string)

      

      The type of user.

      

      

    CreatedTimestamp -> (timestamp)

      

      The time when the user was created.

      

      

    ModifiedTimestamp -> (timestamp)

      

      The time when the user was modified.

      

      

    TimeZoneId -> (string)

      

      The time zone ID of the user.

      

      

    Locale -> (string)

      

      The locale of the user.

      

      

    Storage -> (structure)

      

      The storage for the user.

      

      StorageUtilizedInBytes -> (long)

        

        The amount of storage utilized, in bytes.

        

        

      StorageRule -> (structure)

        

        The storage for a user.

        

        StorageAllocatedInBytes -> (long)

          

          The amount of storage allocated, in bytes.

          

          

        StorageType -> (string)

          

          The type of storage.

          

          

        

      

    

  

TotalNumberOfUsers -> (long)

  

  The total number of users included in the results.

  

  

Marker -> (string)

  

  The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

  

  

