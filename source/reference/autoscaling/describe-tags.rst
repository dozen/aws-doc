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
  [--generate-cli-skeleton]




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

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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
    "NextToken": "None___1",
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

    aws autoscaling describe-tags --filters Name=auto-scaling-group,Values=my-auto-scaling-group --starting-token None___1

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

  

  

