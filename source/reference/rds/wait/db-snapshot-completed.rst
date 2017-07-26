[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` . :ref:`wait <cli:aws rds wait>` ]

.. _cli:aws rds wait db-snapshot-completed:


*********************
db-snapshot-completed
*********************



===========
Description
===========

Wait until DBSnapshotNotFound is thrown when polling with ``describe-db-snapshots``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

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
  [--generate-cli-skeleton]




=======
Options
=======

``--db-instance-identifier`` (string)


  A DB instance identifier to retrieve the list of DB snapshots for. This parameter cannot be used in conjunction with ``DBSnapshotIdentifier`` . This parameter is not case-sensitive. 

   

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
   
  * If this is the identifier of an automated snapshot, the ``SnapshotType`` parameter must also be specified.
   

  

``--snapshot-type`` (string)


  The type of snapshots that will be returned. You can specify one of the following values:

   

   
  * ``automated`` - Return all DB snapshots that have been automatically taken by Amazon RDS for my AWS account.
   
  * ``manual`` - Return all DB snapshots that have been taken by my AWS account.
   
  * ``shared`` - Return all manual DB snapshots that have been shared to my AWS account.
   
  * ``public`` - Return all DB snapshots that have been marked as public.
   

   

  If you do not specify a ``SnapshotType`` , then both automated and manual snapshots are returned. You can include shared snapshots with these results by setting the ``IncludeShared`` parameter to ``true`` . You can include public snapshots with these results by setting the ``IncludePublic`` parameter to ``true`` .

   

  The ``IncludeShared`` and ``IncludePublic`` parameters do not apply for ``SnapshotType`` values of ``manual`` or ``automated`` . The ``IncludePublic`` parameter does not apply when ``SnapshotType`` is set to ``shared`` . the ``IncludeShared`` parameter does not apply when ``SnapshotType`` is set to ``public`` .

  

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


  True to include shared manual DB snapshots from other AWS accounts that this AWS account has been given permission to copy or restore; otherwise false. The default is false.

   

  An AWS account is given permission to restore a manual DB snapshot from another AWS account by the  modify-db-snapshot-attribute API.

  

``--include-public`` | ``--no-include-public`` (boolean)


  True to include manual DB snapshots that are public and can be copied or restored by any AWS account; otherwise false. The default is false.

   

  An manual DB snapshot is shared as public by the  modify-db-snapshot-attribute API.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None