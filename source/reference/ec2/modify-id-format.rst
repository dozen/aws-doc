[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-id-format:


****************
modify-id-format
****************



===========
Description
===========



Modifies the ID format for the specified resource on a per-region basis. You can specify that resources should receive longer IDs (17-character IDs) when they are created. The following resource types support longer IDs: ``instance`` | ``reservation`` .

 

This setting applies to the IAM user who makes the request; it does not apply to the entire AWS account. By default, an IAM user defaults to the same settings as the root user, unless they explicitly override the settings by running this request. Resources created with longer IDs are visible to all IAM users, regardless of these settings and provided that they have permission to use the relevant ``Describe`` command for the resource type.



========
Synopsis
========

::

    modify-id-format
  --resource <value>
  --use-long-ids | --no-use-long-ids
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource`` (string)


  The type of resource.

  

``--use-long-ids`` | ``--no-use-long-ids`` (boolean)


  Indicate whether the resource should use longer IDs (17-character IDs).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To enable the longer ID format for a resource**

This example enables the longer ID format for the ``instance`` resource type. If the request is successful, no output is returned.

Command::

  aws ec2 modify-id-format --resource instance --use-long-ids

**To disable the longer ID format for a resource**

This example disables the longer ID format for the ``instance`` resource type. 

Command::

  aws ec2 modify-id-format --resource instance --no-use-long-ids


======
Output
======

None