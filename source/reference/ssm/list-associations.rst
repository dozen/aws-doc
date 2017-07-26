[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-associations:


*****************
list-associations
*****************



===========
Description
===========



Lists the associations for the specified SSM document or instance.



``list-associations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Associations``


========
Synopsis
========

::

    list-associations
  --association-filter-list <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--association-filter-list`` (list)


  One or more filters. Use a filter to return a more specific list of results.

  



Shorthand Syntax::

    key=string,value=string ...




JSON Syntax::

  [
    {
      "key": "InstanceId"|"Name",
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

**To list your associations for a specific instance**

This example lists all the associations for instance ``i-1a2b3c4d``.

Command::

  aws ssm list-associations --association-filter-list key=InstanceId,value=i-1a2b3c4d

Output::

 {
    "Associations": [
        {
            "InstanceId": "i-1a2b3c4d", 
            "Name": "My_Config_File"
        }
    ]
 }

**To list your associations for a specific configuration document**

This example lists all associations for the configuration document ``My_Config_File``.

Command::

  aws ssm list-associations --association-filter-list key=Name,value=My_Config_File

Output::

 {
    "Associations": [
        {
            "InstanceId": "i-1a2b3c4d", 
            "Name": "My_Config_File"
        }, 
        {
            "InstanceId": "i-rraa3344", 
            "Name": "My_Config_File"
        }
    ]
 }



======
Output
======

Associations -> (list)

  

  The associations.

  

  (structure)

    

    Describes an association of an SSM document and an instance.

    

    Name -> (string)

      

      The name of the SSM document.

      

      

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

