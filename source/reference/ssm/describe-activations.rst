[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-activations:


********************
describe-activations
********************



===========
Description
===========



Details about the activation, including: the date and time the activation was created, the expiration date, the IAM role assigned to the instances in the activation, and the number of instances activated by this registration.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeActivations>`_


``describe-activations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ActivationList``


========
Synopsis
========

::

    describe-activations
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  A filter to view information about your activations.

  



Shorthand Syntax::

    FilterKey=string,FilterValues=string,string ...




JSON Syntax::

  [
    {
      "FilterKey": "ActivationIds"|"DefaultInstanceName"|"IamRole",
      "FilterValues": ["string", ...]
    }
    ...
  ]



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



========
Examples
========

**To describe an activation**

This example provides details about the activations on your account.

Command::

  aws ssm describe-activations

Output::

  {
    "ActivationList": [
        {
            "IamRole": "AutomationRole",
            "RegistrationLimit": 10,
            "ActivationId": "bcf6faa8-83fd-419e-9534-96ad14131eb7",
            "ExpirationDate": 1487887903.045,
            "CreatedDate": 1487801503.045,
            "DefaultInstanceName": "MyWebServers",
            "Expired": false,
            "RegistrationsCount": 0
        }
    ]
  }


======
Output
======

ActivationList -> (list)

  

  A list of activations for your AWS account.

  

  (structure)

    

    An activation registers one or more on-premises servers or virtual machines (VMs) with AWS so that you can configure those servers or VMs using Run Command. A server or VM that has been registered with AWS is called a managed instance.

    

    ActivationId -> (string)

      

      The ID created by Systems Manager when you submitted the activation.

      

      

    Description -> (string)

      

      A user defined description of the activation.

      

      

    DefaultInstanceName -> (string)

      

      A name for the managed instance when it is created.

      

      

    IamRole -> (string)

      

      The Amazon Identity and Access Management (IAM) role to assign to the managed instance.

      

      

    RegistrationLimit -> (integer)

      

      The maximum number of managed instances that can be registered using this activation.

      

      

    RegistrationsCount -> (integer)

      

      The number of managed instances already registered with this activation.

      

      

    ExpirationDate -> (timestamp)

      

      The date when this activation can no longer be used to register managed instances.

      

      

    Expired -> (boolean)

      

      Whether or not the activation is expired.

      

      

    CreatedDate -> (timestamp)

      

      The date the activation was created.

      

      

    

  

NextToken -> (string)

  

  The token for the next set of items to return. Use this token to get the next set of results. 

  

  

