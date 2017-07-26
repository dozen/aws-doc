[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail delete-trail:


************
delete-trail
************



===========
Description
===========



Deletes a trail. This operation must be called from the region in which the trail was created. ``delete-trail`` cannot be called on the shadow trails (replicated trails in other regions) of a trail that is enabled in all regions.



========
Synopsis
========

::

    delete-trail
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  Specifies the name or the CloudTrail ARN of the trail to be deleted. The format of a trail ARN is ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

