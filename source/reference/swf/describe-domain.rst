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
 

 

If the caller does not have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's **cause** parameter will be set to OPERATION_NOT_PERMITTED. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .



========
Synopsis
========

::

    describe-domain
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the domain to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  Contains general information about a domain.

  

  name -> (string)

    

    The name of the domain. This name is unique within the account.

    

    

  status -> (string)

    

    The status of the domain:

     

     
    * **REGISTERED** : The domain is properly registered and available. You can use this domain for registering types and creating new workflow executions. 
     
    * **DEPRECATED** : The domain was deprecated using  deprecate-domain , but is still in use. You should not create new workflow executions in this domain. 
     

    

    

  description -> (string)

    

    The description of the domain provided through  register-domain .

    

    

  

configuration -> (structure)

  

  Contains the configuration settings of a domain.

  

  workflowExecutionRetentionPeriodInDays -> (string)

    

    The retention period for workflow executions in this domain.

    

    

  



.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
