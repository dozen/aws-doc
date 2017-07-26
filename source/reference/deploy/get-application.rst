[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy get-application:


***************
get-application
***************



===========
Description
===========



Gets information about an application.



========
Synopsis
========

::

    get-application
  --application-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of an existing AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about an application**

This example displays information about an application that is associated with the user's AWS account.

Command::

  aws deploy get-application --application-name WordPress_App

Output::

  {
      "application": {
          "applicationName": "WordPress_App",
          "applicationId": "d9dd6993-f171-44fa-a811-211e4EXAMPLE",
          "createTime": 1407878168.078,
		  "linkedToGitHub": false
      }
  }

======
Output
======

application -> (structure)

  

  Information about the application.

  

  applicationId -> (string)

    

    The application ID.

    

    

  applicationName -> (string)

    

    The application name.

    

    

  createTime -> (timestamp)

    

    The time that the application was created.

    

    

  linkedToGitHub -> (boolean)

    

    True if the user has authenticated with GitHub for the specified application; otherwise, false.

    

    

  

