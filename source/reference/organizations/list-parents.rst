[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations list-parents:


************
list-parents
************



===========
Description
===========



Lists the root or organizational units (OUs) that serve as the immediate parent of the specified child OU or account. This operation, along with  list-children enables you to traverse the tree structure that makes up this root.

 

This operation can be called only from the organization's master account.

 

.. note::

   

  In the current release, a child can have only a single parent. 

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/ListParents>`_


``list-parents`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Parents``


========
Synopsis
========

::

    list-parents
  --child-id <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--child-id`` (string)


  The unique identifier (ID) of the OU or account whose parent containers you want to list. Do not specify a root.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a child ID string requires one of the following:

   

   
  * Account: a string that consists of exactly 12 digits. 
   
  * Organizational unit (OU): a string that begins with "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that contains the OU) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits. 
   

  

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

**To list all the parents of a child OU or account**

The following example shows how to list the root or OUs that contain account 444444444444.  

Command::

  aws organizations list-parents --child-id 444444444444

Output::

  {
    "Parents": [
      {
        "Id": "ou-examplerootid111-exampleouid111",
        "Type": "ORGANIZATIONAL_UNIT"
      }
    ]
  }

======
Output
======

Parents -> (list)

  

  A list of parents for the specified child account or OU.

  

  (structure)

    

    Contains information about either a root or an organizational unit (OU) that can contain OUs or accounts in an organization.

    

    Id -> (string)

      

      The unique identifier (ID) of the parent entity.

       

      The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a parent ID string requires one of the following:

       

       
      * Root: a string that begins with "r-" followed by from 4 to 32 lower-case letters or digits. 
       
      * Organizational unit (OU): a string that begins with "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that the OU is in) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits. 
       

      

      

    Type -> (string)

      

      The type of the parent entity.

      

      

    

  

NextToken -> (string)

  

  If present, this value indicates that there is more output available than is included in the current response. Use this value in the ``next-token`` request parameter in a subsequent call to the operation to get the next part of the output. You should repeat this until the ``next-token`` response element comes back as ``null`` .

  

  

