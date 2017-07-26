[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk request-environment-info:


************************
request-environment-info
************************



===========
Description
===========



Initiates a request to compile the specified type of information of the deployed environment.

 

Setting the ``InfoType`` to ``tail`` compiles the last lines from the application server log files of every Amazon EC2 instance in your environment. 

 

Setting the ``InfoType`` to ``bundle`` compresses the application server log files for every Amazon EC2 instance into a ``.zip`` file. Legacy and .NET containers do not support bundle logs. 

 

Use  retrieve-environment-info to obtain the set of logs. 

 

Related Topics

 

 
*  retrieve-environment-info   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/RequestEnvironmentInfo>`_


========
Synopsis
========

::

    request-environment-info
  [--environment-id <value>]
  [--environment-name <value>]
  --info-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--environment-id`` (string)


  The ID of the environment of the requested data.

   

  If no such environment is found, ``request-environment-info`` returns an ``InvalidParameterValue`` error. 

   

  Condition: You must specify either this or an EnvironmentName, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--environment-name`` (string)


  The name of the environment of the requested data.

   

  If no such environment is found, ``request-environment-info`` returns an ``InvalidParameterValue`` error. 

   

  Condition: You must specify either this or an EnvironmentId, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--info-type`` (string)


  The type of information to request.

  

  Possible values:

  
  *   ``tail``

  
  *   ``bundle``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To request tailed logs**

The following command requests logs from an environment named ``my-env``::

  aws elasticbeanstalk request-environment-info --environment-name my-env --info-type tail

After requesting logs, retrieve their location with `retrieve-environment-info`_.

.. _`retrieve-environment-info`: http://docs.aws.amazon.com/cli/latest/reference/elasticbeanstalk/retrieve-environment-info.html


======
Output
======

None