[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf register-domain:


***************
register-domain
***************



===========
Description
===========



Registers a new domain.

 

 **Access Control**  

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* You cannot use an IAM policy to control domain access for this action. The name of the domain being registered is available as the resource of this action. 
 
* Use an ``Action`` element to allow or deny permission to call this action. 
 
* You cannot use an IAM policy to constrain this action's parameters. 
 

 

If the caller doesn't have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's ``cause`` parameter is set to ``OPERATION_NOT_PERMITTED`` . For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows <http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html>`_ in the *Amazon SWF Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/swf-2012-01-25/RegisterDomain>`_


========
Synopsis
========

::

    register-domain
  --name <value>
  [--description <value>]
  --workflow-execution-retention-period-in-days <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Name of the domain to register. The name must be unique in the region that the domain is registered in.

   

  The specified string must not start or end with whitespace. It must not contain a ``:`` (colon), ``/`` (slash), ``|`` (vertical bar), or any control characters (``\u0000-\u001f`` | ``\u007f-\u009f`` ). Also, it must not contain the literal string ``arn`` .

  

``--description`` (string)


  A text description of the domain.

  

``--workflow-execution-retention-period-in-days`` (string)


  The duration (in days) that records and histories of workflow executions on the domain should be kept by the service. After the retention period, the workflow execution isn't available in the results of visibility calls.

   

  If you pass the value ``NONE`` or ``0`` (zero), then the workflow execution history isn't retained. As soon as the workflow execution completes, the execution record and its history are deleted.

   

  The maximum workflow execution retention period is 90 days. For more information about Amazon SWF service limits, see: `Amazon SWF Service Limits <http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dg-limits.html>`_ in the *Amazon SWF Developer Guide* .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

Registering a Domain
--------------------

You can use the AWS CLI to register new domains. Use the ``swf register-domain`` command.  There are two required
parameters, ``--name``, which takes the domain name, and ``--workflow-execution-retention-period-in-days``, which takes
an integer to specify the number of days to retain workflow execution data on this domain, up to a maxium period of 90
days (for more information, see the `SWF FAQ <http://aws.amazon.com/swf/faqs/#retain_limit>`). Workflow execution data
will not be retained after the specified number of days have passed.

Here's an example of registering a new domain:

::

    $ aws swf register-domain --name MyNeatNewDomain --workflow-execution-retention-period-in-days 0
    ""

When you register a domain, nothing is returned (""), but you can use
``swf list-domains`` or ``swf describe-domain`` to see the new domain.
For example:

::

    $ aws swf list-domains --registration-status REGISTERED
    {
        "domainInfos": [
            {
                "status": "REGISTERED",
                "name": "DataFrobotz"
            },
            {
                "status": "REGISTERED",
                "name": "MyNeatNewDomain"
            },
            {
                "status": "REGISTERED",
                "name": "erontest"
            }
        ]
    }

Using ``swf describe-domain``:

::

    aws swf describe-domain --name MyNeatNewDomain
    {
        "domainInfo": {
            "status": "REGISTERED",
            "name": "MyNeatNewDomain"
        },
        "configuration": {
            "workflowExecutionRetentionPeriodInDays": "0"
        }
    }

See Also
--------

-  `RegisterDomain <http://docs.aws.amazon.com/amazonswf/latest/apireference/API_RegisterDomain.html>`__
   in the *Amazon Simple Workflow Service API Reference*



======
Output
======

None