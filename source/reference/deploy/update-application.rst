[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy update-application:


******************
update-application
******************



===========
Description
===========



Changes the name of an application.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/UpdateApplication>`_


========
Synopsis
========

::

    update-application
  [--application-name <value>]
  [--new-application-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The current name of the application you want to change.

  

``--new-application-name`` (string)


  The new name to give the application.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change information about an application**

This example changes the name of an application that is associated with the user's AWS account.

Command::

  aws deploy update-application --application-name WordPress_App --new-application-name My_WordPress_App

Output::

  None.

======
Output
======

None