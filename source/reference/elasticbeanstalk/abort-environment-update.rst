[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk abort-environment-update:


************************
abort-environment-update
************************



===========
Description
===========



Cancels in-progress environment configuration update or application version deployment.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/AbortEnvironmentUpdate>`_


========
Synopsis
========

::

    abort-environment-update
  [--environment-id <value>]
  [--environment-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--environment-id`` (string)


  This specifies the ID of the environment with the in-progress update that you want to cancel.

  

``--environment-name`` (string)


  This specifies the name of the environment with the in-progress update that you want to cancel.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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