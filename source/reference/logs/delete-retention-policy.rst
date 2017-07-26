[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs delete-retention-policy:


***********************
delete-retention-policy
***********************



===========
Description
===========



Deletes the retention policy of the specified log group. Log events would not expire if they belong to log groups without a retention policy. 



========
Synopsis
========

::

    delete-retention-policy
  --log-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group that is associated with the retention policy to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command removes the retention policy that has previously been applied to a log group named ``my-logs``::

  aws logs delete-retention-policy --log-group-name my-logs


======
Output
======

None