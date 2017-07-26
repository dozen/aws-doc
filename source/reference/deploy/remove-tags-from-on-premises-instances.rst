[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy remove-tags-from-on-premises-instances:


**************************************
remove-tags-from-on-premises-instances
**************************************



===========
Description
===========



Removes one or more tags from one or more on-premises instances.



========
Synopsis
========

::

    remove-tags-from-on-premises-instances
  --tags <value>
  --instance-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--tags`` (list)


  The tag key-value pairs to remove from the on-premises instances.

  



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


  The names of the on-premises instances to remove tags from.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To remove tags from one or more on-premises instances**

This example disassociates the same on-premises tag in AWS CodeDeploy from the two specified on-premises instances. It does not deregister the on-premises instances in AWS CodeDeploy, nor uninstall the AWS CodeDeploy Agent from the instance, nor remove the on-premises configuration file from the instances, nor delete the IAM users that are associated with the instances. 

Command::

  aws deploy remove-tags-from-on-premises-instances --instance-names AssetTag12010298EX AssetTag23121309EX --tags Key=Name,Value=CodeDeployDemo-OnPrem

Output::

  This command produces no output.

======
Output
======

None