[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-documents:


**************
list-documents
**************



===========
Description
===========



Describes one or more of your SSM documents.



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
  [--generate-cli-skeleton]




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
      "key": "Name"|"Owner"|"PlatformTypes",
      "value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list all the configuration documents in your account**

This example lists all the configuration documents in your account.

Command::

  aws ssm list-documents

Output::

 {
    "DocumentIdentifiers": [
        {
            "Name": "Config_2"
        }, 
        {
            "Name": "My_Config_Document"
        }
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

      

      

    PlatformTypes -> (list)

      The operating system platform.

      (string)

        

        

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

