[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf describe-domain:


***************
describe-domain
***************



===========
Description
===========



Returns information about the specified domain, including description and status.

 

 **Access Control**  

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains. 
 
* Use an ``Action`` element to allow or deny permission to call this action. 
 
* You cannot use an IAM policy to constrain this action's parameters. 
 

 

If the caller doesn't have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's ``cause`` parameter is set to ``OPERATION_NOT_PERMITTED`` . For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows <http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html>`_ in the *Amazon SWF Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/swf-2012-01-25/DescribeDomain>`_


========
Synopsis
========

::

    describe-domain
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the domain to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

Getting Information About a Domain
----------------------------------

To get detailed information about a particular domain, use the
``swf describe-domain`` command. There is one required parameter:
``--name``, which takes the name of the domain you want information
about. For example:

::

    $ aws swf describe-domain --name DataFrobotz
    {
        "domainInfo": {
            "status": "REGISTERED",
            "name": "DataFrobotz"
        },
        "configuration": {
            "workflowExecutionRetentionPeriodInDays": "1"
        }
    }

You can also use ``describe-domain`` to get information about deprecated
domains:

::

    $ aws swf describe-domain --name MyNeatNewDomain
    {
        "domainInfo": {
            "status": "DEPRECATED",
            "name": "MyNeatNewDomain"
        },
        "configuration": {
            "workflowExecutionRetentionPeriodInDays": "0"
        }
    }

See Also
--------

-  `DescribeDomain <http://docs.aws.amazon.com/amazonswf/latest/apireference/API_DescribeDomain.html>`__
   in the *Amazon Simple Workflow Service API Reference*



======
Output
======

domainInfo -> (structure)

  

  The basic information about a domain, such as its name, status, and description.

  

  name -> (string)

    

    The name of the domain. This name is unique within the account.

    

    

  status -> (string)

    

    The status of the domain:

     

     
    * ``REGISTERED`` – The domain is properly registered and available. You can use this domain for registering types and creating new workflow executions.  
     
    * ``DEPRECATED`` – The domain was deprecated using  deprecate-domain , but is still in use. You should not create new workflow executions in this domain.  
     

    

    

  description -> (string)

    

    The description of the domain provided through  register-domain .

    

    

  

configuration -> (structure)

  

  The domain configuration. Currently, this includes only the domain's retention period.

  

  workflowExecutionRetentionPeriodInDays -> (string)

    

    The retention period for workflow executions in this domain.

    

    

  

