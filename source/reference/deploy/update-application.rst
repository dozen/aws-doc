[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy update-application:


******************
update-application
******************



===========
Description
===========



Changes an existing application's name.



========
Synopsis
========

::

    update-application
  [--application-name <value>]
  [--new-application-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The current name of the application that you want to change.

  

``--new-application-name`` (string)


  The new name that you want to change the application to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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