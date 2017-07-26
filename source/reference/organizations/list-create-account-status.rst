[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations list-create-account-status:


**************************
list-create-account-status
**************************



===========
Description
===========



Lists the account creation requests that match the specified status that is currently being tracked for the organization.

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/ListCreateAccountStatus>`_


``list-create-account-status`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CreateAccountStatuses``


========
Synopsis
========

::

    list-create-account-status
  [--states <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--states`` (list)


  A list of one or more states that you want included in the response. If this parameter is not present, then all requests are included in the response.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    IN_PROGRESS
    SUCCEEDED
    FAILED





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CreateAccountStatuses -> (list)

  

  A list of objects with details about the requests. Certain elements, such as the accountId number, are present in the output only after the account has been successfully created.

  

  (structure)

    

    Contains the status about a  create-account request to create an AWS account in an organization.

    

    Id -> (string)

      

      The unique identifier (ID) that references this request. You get this value from the response of the initial  create-account request to create the account.

       

      The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an create account request ID string requires "car-" followed by from 8 to 32 lower-case letters or digits.

      

      

    AccountName -> (string)

      

      The account name given to the account when it was created.

      

      

    State -> (string)

      

      The status of the request.

      

      

    RequestedTimestamp -> (timestamp)

      

      The date and time that the request was made for the account creation.

      

      

    CompletedTimestamp -> (timestamp)

      

      The date and time that the account was created and the request completed.

      

      

    AccountId -> (string)

      

      If the account was created successfully, the unique identifier (ID) of the new account.

       

      The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an account ID string requires exactly 12 digits.

      

      

    FailureReason -> (string)

      

      If the request failed, a description of the reason for the failure.

       

       
      * ACCOUNT_LIMIT_EXCEEDED: The account could not be created because you have reached the limit on the number of accounts in your organization. 
       
      * EMAIL_ALREADY_EXISTS: The account could not be created because another AWS account with that email address already exists. 
       
      * INVALID_ADDRESS: The account could not be created because the address you provided is not valid. 
       
      * INVALID_EMAIL: The account could not be created because the email address you provided is not valid. 
       
      * INTERNAL_FAILURE: The account could not be created because of an internal failure. Try again later. If the problem persists, contact Customer Support. 
       

      

      

    

  

NextToken -> (string)

  

  If present, this value indicates that there is more output available than is included in the current response. Use this value in the ``next-token`` request parameter in a subsequent call to the operation to get the next part of the output. You should repeat this until the ``next-token`` response element comes back as ``null`` .

  

  

