[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-document-versions:


**********************
list-document-versions
**********************



===========
Description
===========



List all versions for a document.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/ListDocumentVersions>`_


========
Synopsis
========

::

    list-document-versions
  --name <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the document about which you want version information.

  

``--max-results`` (integer)


  The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view details about existing document versions**

This example lists all the versions for a document.

Command::

  aws ssm list-document-versions --name "patchWindowsAmi"

Output::

  {
	"DocumentVersions": [
		{
			"IsDefaultVersion": false, 
			"Name": "patchWindowsAmi", 
			"DocumentVersion": "2", 
			"CreatedDate": 1475799950.484
		}, 
		{
			"IsDefaultVersion": false, 
			"Name": "patchWindowsAmi", 
			"DocumentVersion": "1", 
			"CreatedDate": 1475799931.064
		}
	]
  }


======
Output
======

DocumentVersions -> (list)

  

  The document versions.

  

  (structure)

    

    Version information about the document.

    

    Name -> (string)

      

      The document name.

      

      

    DocumentVersion -> (string)

      

      The document version.

      

      

    CreatedDate -> (timestamp)

      

      The date the document was created.

      

      

    IsDefaultVersion -> (boolean)

      

      An identifier for the default version of the document.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

