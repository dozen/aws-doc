[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy add-tags-to-on-premises-instances:


*********************************
add-tags-to-on-premises-instances
*********************************



===========
Description
===========



Adds tags to on-premises instances.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/AddTagsToOnPremisesInstances>`_


========
Synopsis
========

::

    add-tags-to-on-premises-instances
  --tags <value>
  --instance-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--tags`` (list)


  The tag key-value pairs to add to the on-premises instances.

   

  Keys and values are both required. Keys cannot be null or empty strings. Value-only tags are not allowed.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--instance-names`` (list)


  The names of the on-premises instances to which to add tags.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add tags to on-premises instances**

This example associates in AWS CodeDeploy the same on-premises instance tag to two on-premises instances. It does not register the on-premises instances with AWS CodeDeploy.

Command::

  aws deploy add-tags-to-on-premises-instances --instance-names AssetTag12010298EX AssetTag23121309EX --tags Key=Name,Value=CodeDeployDemo-OnPrem

Output::

  This command produces no output.

======
Output
======

None