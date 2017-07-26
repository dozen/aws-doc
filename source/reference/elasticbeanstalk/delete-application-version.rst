[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk delete-application-version:


**************************
delete-application-version
**************************



===========
Description
===========



Deletes the specified version from the specified application. 

 

.. note::

  You cannot delete an application version that is associated with a running environment.



========
Synopsis
========

::

    delete-application-version
  --application-name <value>
  --version-label <value>
  [--delete-source-bundle | --no-delete-source-bundle]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of the application to delete releases from.

  

``--version-label`` (string)


  The label of the version to delete. 

  

``--delete-source-bundle`` | ``--no-delete-source-bundle`` (boolean)


  Indicates whether to delete the associated source bundle from Amazon S3: 

   

   
  * ``true`` : An attempt is made to delete the associated Amazon S3 source bundle specified at time of creation. 
   
  * ``false`` : No action is taken on the Amazon S3 source bundle specified at time of creation. 
   

   

  Valid Values: ``true`` | ``false``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete an application version**

The following command deletes an application version named ``22a0-stage-150819_182129`` for an application named ``my-app``::

  aws elasticbeanstalk delete-application-version --version-label 22a0-stage-150819_182129 --application-name my-app


======
Output
======

None