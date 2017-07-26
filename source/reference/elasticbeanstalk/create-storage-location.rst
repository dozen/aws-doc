[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk create-storage-location:


***********************
create-storage-location
***********************



===========
Description
===========



Creates the Amazon S3 storage location for the account. 

 

This location is used to store user log files. 



========
Synopsis
========

::

    create-storage-location
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a storage location**

The following command creates a storage location in Amazon S3::

  aws elasticbeanstalk create-storage-location

Output::

  {
      "S3Bucket": "elasticbeanstalk-us-west-2-0123456789012"
  }


======
Output
======

S3Bucket -> (string)

  

  The name of the Amazon S3 bucket created. 

  

  

