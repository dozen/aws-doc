[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf list-workflow-types:


*******************
list-workflow-types
*******************



===========
Description
===========



Returns information about workflow types in the specified domain. The results may be split into multiple pages that can be retrieved by making the call repeatedly.

 

 **Access Control**  

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains. 
 
* Use an ``Action`` element to allow or deny permission to call this action. 
 
* You cannot use an IAM policy to constrain this action's parameters. 
 

 

If the caller doesn't have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's ``cause`` parameter is set to ``OPERATION_NOT_PERMITTED`` . For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows <http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html>`_ in the *Amazon SWF Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/swf-2012-01-25/ListWorkflowTypes>`_


``list-workflow-types`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``typeInfos``


========
Synopsis
========

::

    list-workflow-types
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


  The name of the domain in which the workflow types have been registered.

  

``--name`` (string)


  If specified, lists the workflow type with this name.

  

``--registration-status`` (string)


  Specifies the registration status of the workflow types to list.

  

  Possible values:

  
  *   ``REGISTERED``

  
  *   ``DEPRECATED``

  

  

``--reverse-order`` | ``--no-reverse-order`` (boolean)


  When set to ``true`` , returns the results in reverse order. By default the results are returned in ascending alphabetical order of the ``name`` of the workflow types.

  

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

Listing Workflow Types
----------------------

To get a list of the workflow types for a domain, use ``swf list-workflow-types``. The ``--domain`` and
``--registration-status`` arguments are required. Here's a simple example::

    aws swf list-workflow-types --domain DataFrobtzz --registration-status REGISTERED

Results::

    {
        "typeInfos": [
            {
                "status": "REGISTERED",
                "creationDate": 1371454149.598,
                "description": "DataFrobtzz subscribe workflow",
                "workflowType": {
                    "version": "v3",
                    "name": "subscribe"
                }
            }
        ]
    }

As with ``list-activity-types``, you can use the ``--name`` argument to select only workflow types with a particular
name, and use the ``--maximum-page-size`` argument in coordination with ``--next-page-token`` to page results. To
reverse the order in which results are returned, use ``--reverse-order``.

See Also
--------

-  `ListWorkflowTypes <http://docs.aws.amazon.com/amazonswf/latest/apireference/API_ListWorkflowTypes.html>`_
   in the *Amazon Simple Workflow Service API Reference*



======
Output
======

typeInfos -> (list)

  

  The list of workflow type information.

  

  (structure)

    

    Contains information about a workflow type.

    

    workflowType -> (structure)

      

      The workflow type this information is about.

      

      name -> (string)

        

        The name of the workflow type.

         

        .. note::

           

          The combination of workflow type name and version must be unique with in a domain.

           

        

        

      version -> (string)

        

        The version of the workflow type.

         

        .. note::

           

          The combination of workflow type name and version must be unique with in a domain.

           

        

        

      

    status -> (string)

      

      The current status of the workflow type.

      

      

    description -> (string)

      

      The description of the type registered through  register-workflow-type .

      

      

    creationDate -> (timestamp)

      

      The date when this type was registered.

      

      

    deprecationDate -> (timestamp)

      

      If the type is in deprecated state, then it is set to the date when the type was deprecated.

      

      

    

  

nextPageToken -> (string)

  

  If a ``NextPageToken`` was returned by a previous call, there are more results available. To retrieve the next page of results, make the call again using the returned token in ``nextPageToken`` . Keep all other arguments unchanged.

   

  The configured ``maximumPageSize`` determines how many results can be returned in a single call.

  

  

