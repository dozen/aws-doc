[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk abort-environment-update:


************************
abort-environment-update
************************



===========
Description
===========



Cancels in-progress environment configuration update or application version deployment.



========
Synopsis
========

::

    abort-environment-update
  [--environment-id <value>]
  [--environment-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--environment-id`` (string)


  This specifies the ID of the environment with the in-progress update that you want to cancel.

  

``--environment-name`` (string)


  This specifies the name of the environment with the in-progress update that you want to cancel.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To abort a deployment**

The following command aborts a running application version deployment for an environment named ``my-env``::

  aws elasticbeanstalk abort-environment-update --environment-name my-env


======
Output
======

None