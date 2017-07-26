[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline set-status:


**********
set-status
**********



===========
Description
===========



Requests that the status of the specified physical or logical pipeline objects be updated in the specified pipeline. This update might not occur immediately, but is eventually consistent. The status that can be set depends on the type of object (for example, DataNode or Activity). You cannot perform this operation on ``FINISHED`` pipelines and attempting to do so returns ``InvalidRequestException`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/datapipeline-2012-10-29/SetStatus>`_


========
Synopsis
========

::

    set-status
  --pipeline-id <value>
  --object-ids <value>
  --status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline that contains the objects.

  

``--object-ids`` (list)


  The IDs of the objects. The corresponding objects can be either physical or components, but not a mix of both types.

  



Syntax::

  "string" "string" ...



``--status`` (string)


  The status to be set on all the objects specified in ``objectIds`` . For components, use ``PAUSE`` or ``RESUME`` . For instances, use ``TRY_CANCEL`` , ``RERUN`` , or ``MARK_FINISHED`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON status provided. The JSON status follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None