[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling delete-tags:


***********
delete-tags
***********



===========
Description
===========



Deletes the specified tags.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DeleteTags>`_


========
Synopsis
========

::

    delete-tags
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

**To delete a tag from an Auto Scaling group**

This example deletes the specified tag from the specified Auto Scaling group::

    aws autoscaling delete-tags --tags ResourceId=my-auto-scaling-group,ResourceType=auto-scaling-group,Key=Dept,Value=Research

For more information, see `Tagging Auto Scaling Groups and Instances`_ in the *Auto Scaling Developer Guide*.

.. _`Tagging Auto Scaling Groups and Instances`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ASTagging.html


======
Output
======

None