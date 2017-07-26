[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api list-buckets:


************
list-buckets
************



===========
Description
===========

Returns a list of all buckets owned by the authenticated sender of the request.

========
Synopsis
========

::

    list-buckets
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

The following command uses the ``list-buckets`` command to display the names of all your Amazon S3 buckets (across all
regions)::

  aws s3api list-buckets --query 'Buckets[].Name'

The query option filters the output of ``list-buckets`` down to only the bucket names.

For more information about buckets, see `Working with Amazon S3 Buckets`_ in the *Amazon S3 Developer Guide*.

.. _`Working with Amazon S3 Buckets`: http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingBucket.html


======
Output
======

Buckets -> (list)

  

  (structure)

    

    Name -> (string)

      The name of the bucket.

      

    CreationDate -> (timestamp)

      Date the bucket was created.

      

    

  

Owner -> (structure)

  

  DisplayName -> (string)

    

    

  ID -> (string)

    

    

  

