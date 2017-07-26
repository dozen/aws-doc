[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy batch-get-applications:


**********************
batch-get-applications
**********************



===========
Description
===========



Gets information about one or more applications.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/BatchGetApplications>`_


========
Synopsis
========

::

    batch-get-applications
  [--application-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-names`` (list)


  A list of application names separated by spaces.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about multiple applications**

This example displays information about multiple applications that are associated with the user's AWS account.

Command::

  aws deploy batch-get-applications --application-names WordPress_App MyOther_App

Output::

  {
      "applicationsInfo": [
          {
              "applicationName": "WordPress_App",
              "applicationId": "d9dd6993-f171-44fa-a811-211e4EXAMPLE",
              "createTime": 1407878168.078,
			  "linkedToGitHub": false
          },
          {
              "applicationName": "MyOther_App",
              "applicationId": "8ca57519-31da-42b2-9194-8bb16EXAMPLE",
              "createTime": 1407453571.63,
			  "linkedToGitHub": false
          }
      ]
  }

======
Output
======

applicationsInfo -> (list)

  

  Information about the applications.

  

  (structure)

    

    Information about an application.

    

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

      

      

    

  

