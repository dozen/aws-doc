[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-document-permission:


****************************
describe-document-permission
****************************



===========
Description
===========



Describes the permissions for a Systems Manager document. If you created the document, you are the owner. If a document is shared, it can either be shared privately (by specifying a user's AWS account ID) or publicly (*All* ). 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeDocumentPermission>`_


========
Synopsis
========

::

    describe-document-permission
  --name <value>
  --permission-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the document for which you are the owner.

  

``--permission-type`` (string)


  The permission type for the document. The permission type can be *Share* .

  

  Possible values:

  
  *   ``Share``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the permissions of a document**

This example lists all the versions for a document.

Command::

  aws ssm describe-document-permission --name "RunShellScript" --permission-type "Share"
  
Output::

  {
    "AccountIds": [
        "all"
    ]
  }


======
Output
======

AccountIds -> (list)

  

  The account IDs that have permission to use this document. The ID can be either an AWS account or *All* .

  

  (string)

    

    

  

