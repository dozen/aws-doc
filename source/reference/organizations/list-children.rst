[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations list-children:


*************
list-children
*************



===========
Description
===========



Lists all of the OUs or accounts that are contained in the specified parent OU or root. This operation, along with  list-parents enables you to traverse the tree structure that makes up this root.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/ListChildren>`_


``list-children`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Children``


========
Synopsis
========

::

    list-children
  --parent-id <value>
  --child-type <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--parent-id`` (string)


  The unique identifier (ID) for the parent root or OU whose children you want to list.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a parent ID string requires one of the following:

   

   
  * Root: a string that begins with "r-" followed by from 4 to 32 lower-case letters or digits. 
   
  * Organizational unit (OU): a string that begins with "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that the OU is in) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits. 
   

  

``--child-type`` (string)


  Filters the output to include only the specified child type.

  

  Possible values:

  
  *   ``ACCOUNT``

  
  *   ``ORGANIZATIONAL_UNIT``

  

  

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

**To retrieve a list of all of the child accounts and OUs in a parent root or OU**

The following example shows how to request a list of all of the child OUs in a parent root or OU.  

Command::

  aws organizations list-children --child-type ORGANIZATIONAL_UNIT --parent-id ou-examplerootid111-exampleouid111
  
Output::
  {
    "Children": [
      {
        "Id": "ou-examplerootid111-exampleouid111",
        "Type": "ORGANIZATIONAL_UNIT"
      },
      {
        "Id": "ou-examplerootid111-exampleouid222",
        "Type":"ORGANIZATIONAL_UNIT"
      }
    ]
  }

======
Output
======

Children -> (list)

  

  The list of children of the specified parent container.

  

  (structure)

    

    Contains a list of child entities, either OUs or accounts.

    

    Id -> (string)

      

      The unique identifier (ID) of this child entity.

       

      The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a child ID string requires one of the following:

       

       
      * Account: a string that consists of exactly 12 digits. 
       
      * Organizational unit (OU): a string that begins with "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that contains the OU) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits. 
       

      

      

    Type -> (string)

      

      The type of this child entity.

      

      

    

  

NextToken -> (string)

  

  If present, this value indicates that there is more output available than is included in the current response. Use this value in the ``next-token`` request parameter in a subsequent call to the operation to get the next part of the output. You should repeat this until the ``next-token`` response element comes back as ``null`` .

  

  

