[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy create-application:


******************
create-application
******************



===========
Description
===========



Creates a new application.



========
Synopsis
========

::

    create-application
  --application-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of the application. This name must be unique with the applicable IAM user or AWS account.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an application**

This example creates an application and associates it with the user's AWS account.

Command::

  aws deploy create-application --application-name MyOther_App
  
Output::

  {
      "applicationId": "cfd3e1f1-5744-4aee-9251-eaa25EXAMPLE"
  }

======
Output
======

applicationId -> (string)

  

  A unique application ID.

  

  

