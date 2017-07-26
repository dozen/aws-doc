[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling create-or-update-tags:


*********************
create-or-update-tags
*********************



===========
Description
===========



Creates or updates tags for the specified Auto Scaling group.

 

When you specify a tag with a key that already exists, the operation overwrites the previous tag definition, and you do not get an error message.

 

For more information, see `Tagging Auto Scaling Groups and Instances <http://docs.aws.amazon.com/autoscaling/latest/userguide/autoscaling-tagging.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/CreateOrUpdateTags>`_


========
Synopsis
========

::

    create-or-update-tags
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--tags`` (list)


  One or more tags.

  



Shorthand Syntax::

    ResourceId=string,ResourceType=string,Key=string,Value=string,PropagateAtLaunch=boolean ...




JSON Syntax::

  [
    {
      "ResourceId": "string",
      "ResourceType": "string",
      "Key": "string",
      "Value": "string",
      "PropagateAtLaunch": true|false
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create or update tags for an Auto Scaling group**

This example adds two tags to the specified Auto Scaling group::

    aws autoscaling create-or-update-tags --tags ResourceId=my-auto-scaling-group,ResourceType=auto-scaling-group,Key=Role,Value=WebServer,PropagateAtLaunch=true ResourceId=my-auto-scaling-group,ResourceType=auto-scaling-group,Key=Dept,Value=Research,PropagateAtLaunch=true


======
Output
======

None