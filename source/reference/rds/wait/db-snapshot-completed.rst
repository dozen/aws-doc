[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` . :ref:`wait <cli:aws rds wait>` ]

.. _cli:aws rds wait db-snapshot-completed:


*********************
db-snapshot-completed
*********************



===========
Description
===========

Wait until DBSnapshotNotFound is thrown when polling with ``describe-db-snapshots``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeDBSnapshots>`_


``db-snapshot-completed`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DBSnapshots``


========
Synopsis
========

::

    db-snapshot-completed
  [--db-instance-identifier <value>]
  [--db-snapshot-identifier <value>]
  [--snapshot-type <value>]
  [--filters <value>]
  [--include-shared | --no-include-shared]
  [--include-public | --no-include-public]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-instance-identifier`` (string)


  The ID of the DB instance to retrieve the list of DB snapshots for. This parameter cannot be used in conjunction with ``DBSnapshotIdentifier`` . This parameter is not case-sensitive. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

  

``--db-snapshot-identifier`` (string)


  A specific DB snapshot identifier to describe. This parameter cannot be used in conjunction with ``DBInstanceIdentifier`` . This value is stored as a lowercase string. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters. 
   
  * First character must be a letter. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   
  * If this identifier is for an automated snapshot, the ``SnapshotType`` parameter must also be specified. 
   

  

``--snapshot-type`` (string)


  The type of snapshots to be returned. You can specify one of the following values:

   

   
  * ``automated`` - Return all DB snapshots that have been automatically taken by Amazon RDS for my AWS account. 
   
  * ``manual`` - Return all DB snapshots that have been taken by my AWS account. 
   
  * ``shared`` - Return all manual DB snapshots that have been shared to my AWS account. 
   
  * ``public`` - Return all DB snapshots that have been marked as public. 
   

   

  If you don't specify a ``SnapshotType`` value, then both automated and manual snapshots are returned. Shared and public DB snapshots are not included in the returned results by default. You can include shared snapshots with these results by setting the ``IncludeShared`` parameter to ``true`` . You can include public snapshots with these results by setting the ``IncludePublic`` parameter to ``true`` .

   

  The ``IncludeShared`` and ``IncludePublic`` parameters don't apply for ``SnapshotType`` values of ``manual`` or ``automated`` . The ``IncludePublic`` parameter doesn't apply when ``SnapshotType`` is set to ``shared`` . The ``IncludeShared`` parameter doesn't apply when ``SnapshotType`` is set to ``public`` .

  

``--filters`` (list)


  This parameter is not currently supported.

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--include-shared`` | ``--no-include-shared`` (boolean)


  Set this value to ``true`` to include shared manual DB snapshots from other AWS accounts that this AWS account has been given permission to copy or restore, otherwise set this value to ``false`` . The default is ``false`` .

   

  You can give an AWS account permission to restore a manual DB snapshot from another AWS account by using the  modify-db-snapshot-attribute API action.

  

``--include-public`` | ``--no-include-public`` (boolean)


  Set this value to ``true`` to include manual DB snapshots that are public and can be copied or restored by any AWS account, otherwise set this value to ``false`` . The default is ``false`` .

   

  You can share a manual DB snapshot as public by using the  modify-db-snapshot-attribute API.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None