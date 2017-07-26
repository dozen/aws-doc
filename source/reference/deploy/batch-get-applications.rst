[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy batch-get-applications:


**********************
batch-get-applications
**********************



===========
Description
===========



Gets information about one or more applications.



========
Synopsis
========

::

    batch-get-applications
  [--application-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-names`` (list)


  A list of application names, with multiple application names separated by spaces.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      The time that the application was created.

      

      

    linkedToGitHub -> (boolean)

      

      True if the user has authenticated with GitHub for the specified application; otherwise, false.

      

      

    

  

