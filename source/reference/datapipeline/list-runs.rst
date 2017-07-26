[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline list-runs:


*********
list-runs
*********



===========
Description
===========

Lists the times the specified pipeline has run. You can optionally filter the complete list of results to include only the runs you are interested in.



========
Synopsis
========

::

    list-runs
  --pipeline-id <value>
  [--status <value>]
  [--start-interval <value>]
  [--schedule-interval <value>]




=======
Options
=======

``--pipeline-id`` (string)
The identifier of the pipeline.

``--status`` (string)
Filters the list to include only runs in the specified statuses. The valid statuses are as follows: waiting, pending, cancelled, running, finished, failed, waiting_for_runner, and waiting_on_dependencies.

``--start-interval`` (string)
Filters the list to include only runs that started within the specified interval.

``--schedule-interval`` (string)
Filters the list to include only runs that are scheduled to start within the specified interval.



========
Examples
========

**To list your pipeline runs**

This example lists the runs for the specified pipeline::

   aws datapipeline list-runs --pipeline-id df-00627471SOVYZEXAMPLE
   
The following is example output::

       Name                       Scheduled Start        Status                     ID                                              Started                Ended
   -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
   1.  EC2ResourceObj             2015-04-12T17:33:02    CREATING                   @EC2ResourceObj_2015-04-12T17:33:02             2015-04-12T17:33:10

   2.  S3InputLocation            2015-04-12T17:33:02    FINISHED                   @S3InputLocation_2015-04-12T17:33:02            2015-04-12T17:33:09    2015-04-12T17:33:09

   3.  S3OutputLocation           2015-04-12T17:33:02    WAITING_ON_DEPENDENCIES    @S3OutputLocation_2015-04-12T17:33:02           2015-04-12T17:33:09

   4.  ShellCommandActivityObj    2015-04-12T17:33:02    WAITING_FOR_RUNNER         @ShellCommandActivityObj_2015-04-12T17:33:02    2015-04-12T17:33:09
