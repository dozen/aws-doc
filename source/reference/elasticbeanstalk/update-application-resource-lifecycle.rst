[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk update-application-resource-lifecycle:


*************************************
update-application-resource-lifecycle
*************************************



===========
Description
===========



Modifies lifecycle settings for an application.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/UpdateApplicationResourceLifecycle>`_


========
Synopsis
========

::

    update-application-resource-lifecycle
  --application-name <value>
  --resource-lifecycle-config <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application.

  

``--resource-lifecycle-config`` (structure)


  The lifecycle configuration.

  



Shorthand Syntax::

    ServiceRole=string,VersionLifecycleConfig={MaxCountRule={Enabled=boolean,MaxCount=integer,DeleteSourceFromS3=boolean},MaxAgeRule={Enabled=boolean,MaxAgeInDays=integer,DeleteSourceFromS3=boolean}}




JSON Syntax::

  {
    "ServiceRole": "string",
    "VersionLifecycleConfig": {
      "MaxCountRule": {
        "Enabled": true|false,
        "MaxCount": integer,
        "DeleteSourceFromS3": true|false
      },
      "MaxAgeRule": {
        "Enabled": true|false,
        "MaxAgeInDays": integer,
        "DeleteSourceFromS3": true|false
      }
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ApplicationName -> (string)

  

  The name of the application.

  

  

ResourceLifecycleConfig -> (structure)

  

  The lifecycle configuration.

  

  ServiceRole -> (string)

    

    The ARN of an IAM service role that Elastic Beanstalk has permission to assume.

    

    

  VersionLifecycleConfig -> (structure)

    

    The application version lifecycle configuration.

    

    MaxCountRule -> (structure)

      

      Specify a max count rule to restrict the number of application versions that are retained for an application.

      

      Enabled -> (boolean)

        

        Specify ``true`` to apply the rule, or ``false`` to disable it.

        

        

      MaxCount -> (integer)

        

        Specify the maximum number of application versions to retain.

        

        

      DeleteSourceFromS3 -> (boolean)

        

        Set to ``true`` to delete a version's source bundle from Amazon S3 when Elastic Beanstalk deletes the application version.

        

        

      

    MaxAgeRule -> (structure)

      

      Specify a max age rule to restrict the length of time that application versions are retained for an application.

      

      Enabled -> (boolean)

        

        Specify ``true`` to apply the rule, or ``false`` to disable it.

        

        

      MaxAgeInDays -> (integer)

        

        Specify the number of days to retain an application versions.

        

        

      DeleteSourceFromS3 -> (boolean)

        

        Set to ``true`` to delete a version's source bundle from Amazon S3 when Elastic Beanstalk deletes the application version.

        

        

      

    

  

