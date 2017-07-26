[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-id-format:


****************
modify-id-format
****************



===========
Description
===========



Modifies the ID format for the specified resource on a per-region basis. You can specify that resources should receive longer IDs (17-character IDs) when they are created. The following resource types support longer IDs: ``instance`` | ``reservation`` | ``snapshot`` | ``volume`` .

 

This setting applies to the IAM user who makes the request; it does not apply to the entire AWS account. By default, an IAM user defaults to the same settings as the root user. If you're using this action as the root user, then these settings apply to the entire account, unless an IAM user explicitly overrides these settings for themselves. For more information, see `Resource IDs <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/resource-ids.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . 

 

Resources created with longer IDs are visible to all IAM roles and users, regardless of these settings and provided that they have permission to use the relevant ``Describe`` command for the resource type.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifyIdFormat>`_


========
Synopsis
========

::

    modify-id-format
  --resource <value>
  --use-long-ids | --no-use-long-ids
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource`` (string)


  The type of resource: ``instance`` | ``reservation`` | ``snapshot`` | ``volume``  

  

``--use-long-ids`` | ``--no-use-long-ids`` (boolean)


  Indicate whether the resource should use longer IDs (17-character IDs).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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