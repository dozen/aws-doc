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

 

For more information, see `Tagging Auto Scaling Groups and Instances`_ in the *Auto Scaling Developer Guide* .



========
Synopsis
========

::

    create-or-update-tags
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

.. _Tagging Auto Scaling Groups and Instances: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ASTagging.html
