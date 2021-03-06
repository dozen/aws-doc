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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/CreateStorageLocation>`_


========
Synopsis
========

::

    create-storage-location
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

