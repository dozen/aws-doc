[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-applications:


*********************
describe-applications
*********************



===========
Description
===========



Returns the descriptions of existing applications.



========
Synopsis
========

::

    describe-applications
  [--application-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-names`` (list)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to only include those with the specified names. 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view a list of applications**

The following command retrieves information about applications in the current region::

  aws elasticbeanstalk describe-applications

Output::

  {
      "Applications": [
          {
              "ApplicationName": "ruby",
              "ConfigurationTemplates": [],
              "DateUpdated": "2015-08-13T21:05:44.376Z",
              "Versions": [
                  "Sample Application"
              ],
              "DateCreated": "2015-08-13T21:05:44.376Z"
          },
          {
              "ApplicationName": "pythonsample",
              "Description": "Application created from the EB CLI using \"eb init\"",
              "Versions": [
                  "Sample Application"
              ],
              "DateCreated": "2015-08-13T19:05:43.637Z",
              "ConfigurationTemplates": [],
              "DateUpdated": "2015-08-13T19:05:43.637Z"
          },
          {
              "ApplicationName": "nodejs-example",
              "ConfigurationTemplates": [],
              "DateUpdated": "2015-08-06T17:50:02.486Z",
              "Versions": [
                  "add elasticache",
                  "First Release"
              ],
              "DateCreated": "2015-08-06T17:50:02.486Z"
          }
      ]
  }


======
Output
======

Applications -> (list)

  

  This parameter contains a list of  ApplicationDescription . 

  

  (structure)

    

    Describes the properties of an application.

    

    ApplicationName -> (string)

      

      The name of the application.

      

      

    Description -> (string)

      

      User-defined description of the application.

      

      

    DateCreated -> (timestamp)

      

      The date when the application was created.

      

      

    DateUpdated -> (timestamp)

      

      The date when the application was last modified.

      

      

    Versions -> (list)

      

      The names of the versions for this application.

      

      (string)

        

        

      

    ConfigurationTemplates -> (list)

      

      The names of the configuration templates associated with this application. 

      

      (string)

        

        

      

    

  

