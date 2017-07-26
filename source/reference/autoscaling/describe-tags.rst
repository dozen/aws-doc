[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-tags:


*************
describe-tags
*************



===========
Description
===========



Describes the specified tags.

 

You can use filters to limit the results. For example, you can query for the tags for a specific Auto Scaling group. You can specify multiple values for a filter. A tag must match at least one of the specified values for it to be included in the results.

 

You can also specify multiple filters. The result includes information for a particular tag only if it matches all the filters. If there's no match, no special message is returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeTags>`_


``describe-tags`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Tags``


========
Synopsis
========

::

    describe-tags
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


  A filter used to scope the tags to return.

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



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

**To describe tags**

This example describes all your tags::

    aws autoscaling describe-tags

The following is example output::

    {
        "Tags": [
            {
                "ResourceType": "auto-scaling-group",
                "ResourceId": "my-auto-scaling-group",
                "PropagateAtLaunch": true,
                "Value": "Research",
                "Key": "Dept"
            },
            {
                "ResourceType": "auto-scaling-group",
                "ResourceId": "my-auto-scaling-group",
                "PropagateAtLaunch": true,
                "Value": "WebServer",
                "Key": "Role"
            }
        ]
    }

To describe tags for a specific Auto Scaling group, use the ``filters`` parameter::

    aws autoscaling describe-tags --filters Name=auto-scaling-group,Values=my-auto-scaling-group

To return a specific number of tags, use the ``max-items`` parameter::

    aws autoscaling describe-tags --max-items 1

The following is example output::

    {
        "NextToken": "Z3M3LMPEXAMPLE",
        "Tags": [
            {
                "ResourceType": "auto-scaling-group",
                "ResourceId": "my-auto-scaling-group",
                "PropagateAtLaunch": true,
                "Value": "Research",
                "Key": "Dept"
            }
        ]
    }

Use the ``NextToken`` field with the ``starting-token`` parameter in a subsequent call to get the additional tags::

    aws autoscaling describe-tags --filters Name=auto-scaling-group,Values=my-auto-scaling-group --starting-token Z3M3LMPEXAMPLE

For more information, see `Tagging Auto Scaling Groups and Instances`_ in the *Auto Scaling Developer Guide*.

.. _`Tagging Auto Scaling Groups and Instances`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ASTagging.html


======
Output
======

Tags -> (list)

  

  One or more tags.

  

  (structure)

    

    Describes a tag for an Auto Scaling group.

    

    ResourceId -> (string)

      

      The name of the group.

      

      

    ResourceType -> (string)

      

      The type of resource. The only supported value is ``auto-scaling-group`` .

      

      

    Key -> (string)

      

      The tag key.

      

      

    Value -> (string)

      

      The tag value.

      

      

    PropagateAtLaunch -> (boolean)

      

      Determines whether the tag is added to new instances as they are launched in the group.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

