[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-documents:


**************
list-documents
**************



===========
Description
===========



Describes one or more of your SSM documents.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/ListDocuments>`_


``list-documents`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DocumentIdentifiers``


========
Synopsis
========

::

    list-documents
  [--document-filter-list <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--document-filter-list`` (list)


  One or more filters. Use a filter to return a more specific list of results.

  



Shorthand Syntax::

    key=string,value=string ...




JSON Syntax::

  [
    {
      "key": "Name"|"Owner"|"PlatformTypes"|"DocumentType",
      "value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list all the configuration documents in your account**

This example lists all the documents in your account.

Command::

  aws ssm list-documents

Output::

  {
	"DocumentIdentifiers": [
		{
			"Name": "AWS-ApplyPatchBaseline",
			"PlatformTypes": [
				"Windows"
			],
			"DocumentVersion": "1",
			"DocumentType": "Command",
			"Owner": "Amazon",
			"SchemaVersion": "1.2"
		},
		{
			"Name": "AWS-ConfigureAWSPackage",
			"PlatformTypes": [
				"Windows",
				"Linux"
			],
			"DocumentVersion": "1",
			"DocumentType": "Command",
			"Owner": "Amazon",
			"SchemaVersion": "2.0"
		},
		...
	]
  }


======
Output
======

DocumentIdentifiers -> (list)

  

  The names of the SSM documents.

  

  (structure)

    

    Describes the name of an SSM document.

    

    Name -> (string)

      

      The name of the SSM document.

      

      

    Owner -> (string)

      

      The AWS user account of the person who created the document.

      

      

    PlatformTypes -> (list)

      

      The operating system platform. 

      

      (string)

        

        

      

    DocumentVersion -> (string)

      

      The document version.

      

      

    DocumentType -> (string)

      

      The document type.

      

      

    SchemaVersion -> (string)

      

      The schema version.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

