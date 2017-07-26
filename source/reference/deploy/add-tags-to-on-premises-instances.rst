[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy add-tags-to-on-premises-instances:


*********************************
add-tags-to-on-premises-instances
*********************************



===========
Description
===========



Adds tags to on-premises instances.



========
Synopsis
========

::

    add-tags-to-on-premises-instances
  --tags <value>
  --instance-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--tags`` (list)


  The tag key-value pairs to add to the on-premises instances.

   

  Keys and values are both required. Keys cannot be nulls or empty strings. Value-only tags are not allowed.

  



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


  The names of the on-premises instances to add tags to.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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