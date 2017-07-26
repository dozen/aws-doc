[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` . :ref:`wait <cli:aws redshift wait>` ]

.. _cli:aws redshift wait snapshot-available:


******************
snapshot-available
******************



===========
Description
===========

Wait until JMESPath query Snapshots[].Status returns available for all elements when polling with ``describe-cluster-snapshots``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 20 failed checks.

``snapshot-available`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Snapshots``


========
Synopsis
========

::

    snapshot-available
  [--cluster-identifier <value>]
  [--snapshot-identifier <value>]
  [--snapshot-type <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--owner-account <value>]
  [--tag-keys <value>]
  [--tag-values <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-identifier`` (string)


  The identifier of the cluster for which information about snapshots is requested. 

  

``--snapshot-identifier`` (string)


  The snapshot identifier of the snapshot about which to return information. 

  

``--snapshot-type`` (string)


  The type of snapshots for which you are requesting information. By default, snapshots of all types are returned. 

   

  Valid Values: ``automated`` | ``manual``  

  

``--start-time`` (timestamp)


  A value that requests only snapshots created at or after the specified time. The time value is specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page.`_  

   

  Example: ``2012-07-16T18:00:00Z`` 

  

``--end-time`` (timestamp)


  A time value that requests only snapshots created at or before the specified time. The time value is specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page.`_  

   

  Example: ``2012-07-16T18:00:00Z`` 

  

``--owner-account`` (string)


  The AWS customer account used to create or copy the snapshot. Use this field to filter the results to snapshots owned by a particular account. To describe snapshots you own, either specify your AWS customer account, or do not specify the parameter. 

  

``--tag-keys`` (list)


  A tag key or keys for which you want to return all matching cluster snapshots that are associated with the specified key or keys. For example, suppose that you have snapshots that are tagged with keys called ``owner`` and ``environment`` . If you specify both of these tag keys in the request, Amazon Redshift returns a response with the snapshots that have either or both of these tag keys associated with them.

  



Syntax::

  "string" "string" ...



``--tag-values`` (list)


  A tag value or values for which you want to return all matching cluster snapshots that are associated with the specified tag value or values. For example, suppose that you have snapshots that are tagged with values called ``admin`` and ``test`` . If you specify both of these tag values in the request, Amazon Redshift returns a response with the snapshots that have either or both of these tag values associated with them.

  



Syntax::

  "string" "string" ...



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

.. _ISO8601 Wikipedia page.: http://en.wikipedia.org/wiki/ISO_8601
