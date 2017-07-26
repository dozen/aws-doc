[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector update-assessment-target:


************************
update-assessment-target
************************



===========
Description
===========



Updates the assessment target that is specified by the ARN of the assessment target.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/UpdateAssessmentTarget>`_


========
Synopsis
========

::

    update-assessment-target
  --assessment-target-arn <value>
  --assessment-target-name <value>
  --resource-group-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-target-arn`` (string)


  The ARN of the assessment target that you want to update.

  

``--assessment-target-name`` (string)


  The name of the assessment target that you want to update.

  

``--resource-group-arn`` (string)


  The ARN of the resource group that is used to specify the new resource group to associate with the assessment target.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update an assessment target**

The following ``update-assessment-target`` command updates the assessment target with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX`` and the name of ``Example``, and the resource group with the ARN of ``arn:aws:inspector:us-west-2:123456789012:resourcegroup/0-yNbgL5Pt``::

  aws inspector update-assessment-target --assessment-target-arn arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX --assessment-target-name Example --resource-group-arn arn:aws:inspector:us-west-2:123456789012:resourcegroup/0-yNbgL5Pt

For more information, see `Amazon Inspector Assessment Targets`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Targets`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_applications.html



======
Output
======

None