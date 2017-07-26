[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations describe-create-account-status:


******************************
describe-create-account-status
******************************



===========
Description
===========



Retrieves the current status of an asynchronous request to create an account.

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/DescribeCreateAccountStatus>`_


========
Synopsis
========

::

    describe-create-account-status
  --create-account-request-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--create-account-request-id`` (string)


  Specifies the ``operationId`` that uniquely identifies the request. You can get the ID from the response to an earlier  create-account request, or from the  list-create-account-status operation.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an create account request ID string requires "car-" followed by from 8 to 32 lower-case letters or digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the latest status about a request to create an account**

The following example shows how to request the latest status for a previous request to create an account in an organization. The specified --request-id comes from the response of the original call to create-account. The account creation request shows by the status field that Organizations successfully completed the creation of the account.

Command::

  aws organizations describe-create-account-status --create-account-request-id car-examplecreateaccountrequestid111
  
Output::

  {
    "CreateAccountStatus": {
      "State": "SUCCEEDED",
      "AccountId": "555555555555",
      "AccountName": "Beta account",
      "RequestedTimestamp": 1470684478.687,
      "CompletedTimestamp": 1470684532.472,
      "Id": "car-examplecreateaccountrequestid111"
    }
  }


======
Output
======

CreateAccountStatus -> (structure)

  

  A structure that contains the current status of an account creation request.

  

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
     

    

    

  

