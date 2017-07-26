[ :ref:`aws <cli:aws>` . :ref:`elastictranscoder <cli:aws elastictranscoder>` ]

.. _cli:aws elastictranscoder test-role:


*********
test-role
*********



===========
Description
===========



The test-role operation tests the IAM role used to create the pipeline.

 

The ``test-role`` action lets you determine whether the IAM role you are using has sufficient permissions to let Elastic Transcoder perform tasks associated with the transcoding process. The action attempts to assume the specified IAM role, checks read access to the input and output buckets, and tries to send a test notification to Amazon SNS topics that you specify.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elastictranscoder-2012-09-25/TestRole>`_


========
Synopsis
========

::

    test-role
  --role <value>
  --input-bucket <value>
  --output-bucket <value>
  --topics <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role`` (string)


  The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to test.

  

``--input-bucket`` (string)


  The Amazon S3 bucket that contains media files to be transcoded. The action attempts to read from this bucket.

  

``--output-bucket`` (string)


  The Amazon S3 bucket that Elastic Transcoder writes transcoded media files to. The action attempts to read from this bucket.

  

``--topics`` (list)


  The ARNs of one or more Amazon Simple Notification Service (Amazon SNS) topics that you want the action to send a test notification to.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Success -> (string)

  

  If the operation is successful, this value is ``true`` ; otherwise, the value is ``false`` .

  

  

Messages -> (list)

  

  If the ``Success`` element contains ``false`` , this value is an array of one or more error messages that were generated during the test process.

  

  (string)

    

    

  

