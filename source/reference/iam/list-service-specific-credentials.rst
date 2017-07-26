[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-service-specific-credentials:


*********************************
list-service-specific-credentials
*********************************



===========
Description
===========



Returns information about the service-specific credentials associated with the specified IAM user. If there are none, the action returns an empty list. The service-specific credentials returned by this action are used only for authenticating the IAM user to a specific service. For more information about using service-specific credentials to authenticate to an AWS service, see `Set Up service-specific credentials <http://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-gc.html>`_ in the AWS CodeCommit User Guide.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/ListServiceSpecificCredentials>`_


========
Synopsis
========

::

    list-service-specific-credentials
  [--user-name <value>]
  [--service-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the user whose service-specific credentials you want information about. If this value is not specified then the operation assumes the user whose credentials are used to call the operation.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--service-name`` (string)


  Filters the returned results to only those for the specified AWS service. If not specified, then AWS returns service-specific credentials for all services.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ServiceSpecificCredentials -> (list)

  

  A list of structures that each contain details about a service-specific credential.

  

  (structure)

    

    Contains additional details about a service-specific credential.

    

    UserName -> (string)

      

      The name of the IAM user associated with the service-specific credential.

      

      

    Status -> (string)

      

      The status of the service-specific credential. ``Active`` means the key is valid for API calls, while ``Inactive`` means it is not.

      

      

    ServiceUserName -> (string)

      

      The generated user name for the service-specific credential.

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the service-specific credential were created.

      

      

    ServiceSpecificCredentialId -> (string)

      

      The unique identifier for the service-specific credential.

      

      

    ServiceName -> (string)

      

      The name of the service associated with the service-specific credential.

      

      

    

  

