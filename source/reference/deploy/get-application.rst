[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy get-application:


***************
get-application
***************



===========
Description
===========



Gets information about an application.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/GetApplication>`_


========
Synopsis
========

::

    get-application
  --application-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    The time at which the application was created.

    

    

  linkedToGitHub -> (boolean)

    

    True if the user has authenticated with GitHub for the specified application; otherwise, false.

    

    

  gitHubAccountName -> (string)

    

    The name for a connection to a GitHub account.

    

    

  

