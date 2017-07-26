[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail delete-trail:


************
delete-trail
************



===========
Description
===========



Deletes a trail. This operation must be called from the region in which the trail was created. ``delete-trail`` cannot be called on the shadow trails (replicated trails in other regions) of a trail that is enabled in all regions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudtrail-2013-11-01/DeleteTrail>`_


========
Synopsis
========

::

    delete-trail
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Specifies the name or the CloudTrail ARN of the trail to be deleted. The format of a trail ARN is: ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a trail**

The following ``delete-trail`` command deletes a trail named ``Trail1``::

  aws cloudtrail delete-trail --name Trail1
  

======
Output
======

