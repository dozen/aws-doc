[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory get-directory:


*************
get-directory
*************



===========
Description
===========



Retrieves metadata about a directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/GetDirectory>`_


========
Synopsis
========

::

    get-directory
  --directory-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The ARN of the directory.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Directory -> (structure)

  

  Metadata about the directory.

  

  Name -> (string)

    

    The name of the directory.

    

    

  DirectoryArn -> (string)

    

    The Amazon Resource Name (ARN) that is associated with the directory. For more information, see  arns .

    

    

  State -> (string)

    

    The state of the directory. Can be either ``Enabled`` , ``Disabled`` , or ``Deleted`` .

    

    

  CreationDateTime -> (timestamp)

    

    The date and time when the directory was created.

    

    

  

