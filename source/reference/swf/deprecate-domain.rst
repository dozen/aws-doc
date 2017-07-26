[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf deprecate-domain:


****************
deprecate-domain
****************



===========
Description
===========



Deprecates the specified domain. After a domain has been deprecated it cannot be used to create new workflow executions or register new types. However, you can still use visibility actions on this domain. Deprecating a domain also deprecates all activity and workflow types registered in the domain. Executions that were started before the domain was deprecated will continue to run.

 

.. note::

  This operation is eventually consistent. The results are best effort and may not exactly reflect recent updates and changes.

 

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

    deprecate-domain
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the domain to deprecate.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Deprecating a Domain
--------------------

To deprecate a domain (you can still see it, but cannot create new
workflow executions or register types on it), use
``swf deprecate-domain``. It has a sole required parameter, ``--name``,
which takes the name of the domain to deprecate.

::

    $ aws swf deprecate-domain --name MyNeatNewDomain
    ""

As with ``register-domain``, no output is returned. If you use
``list-domains`` to view the registered domains, however, you will see
that the domain has been deprecated and no longer appears in the
returned data:

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
                "name": "erontest"
            }
        ]
    }

If you use ``--registration-status DEPRECATED`` with ``list-domains``,
you will see your deprecated domain:

::

    $ aws swf list-domains --registration-status DEPRECATED
    {
        "domainInfos": [
            {
                "status": "DEPRECATED",
                "name": "MyNeatNewDomain"
            }
        ]
    }

You can still use ``describe-domain`` to get information about a
deprecated domain:

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

-  `DeprecateDomain <http://docs.aws.amazon.com/amazonswf/latest/apireference/API_DeprecateDomain.html>`__
   in the *Amazon Simple Workflow Service API Reference*



======
Output
======

None

.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
