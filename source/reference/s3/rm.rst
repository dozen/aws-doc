[ :ref:`aws <cli:aws>` . :ref:`s3 <cli:aws s3>` ]

.. _cli:aws s3 rm:


**
rm
**



===========
Description
===========

Deletes an S3 object.



========
Synopsis
========

::

    rm
  <S3Uri>
  [--dryrun]
  [--quiet]
  [--recursive]
  [--include <value>]
  [--exclude <value>]
  [--only-show-errors]
  [--page-size <value>]




=======
Options
=======

``paths`` (string)


``--dryrun`` (boolean)
Displays the operations that would be performed using the specified command without actually running them.

``--quiet`` (boolean)
Does not display the operations performed from the specified command.

``--recursive`` (boolean)
Command is performed on all files or objects under the specified directory or prefix.

``--include`` (string)
Don't exclude files or objects in the command that match the specified pattern. See `Use of Exclude and Include Filters`_ for details.

``--exclude`` (string)
Exclude all files or objects from the command that matches the specified pattern.

``--only-show-errors`` (boolean)
Only errors and warnings are displayed. All other output is suppressed.

``--page-size`` (integer)
The number of results to return in each response to a list operation. The default value is 1000 (the maximum allowed). Using a lower value may help if an operation times out.



========
Examples
========

The following ``rm`` command deletes a single s3 object::

    aws s3 rm s3://mybucket/test2.txt

Output::

    delete: s3://mybucket/test2.txt

The following ``rm`` command recursively deletes all objects under a specified bucket and prefix when passed with the
parameter ``--recursive``.  In this example, the bucket ``mybucket`` contains the objects ``test1.txt`` and
``test2.txt``::

    aws s3 rm s3://mybucket --recursive

Output::

    delete: s3://mybucket/test1.txt
    delete: s3://mybucket/test2.txt

The following ``rm`` command recursively deletes all objects under a specified bucket and prefix when passed with the
parameter ``--recursive`` while excluding some objects by using an ``--exclude`` parameter.  In this example, the bucket
``mybucket`` has the objects ``test1.txt`` and ``test2.jpg``::

    aws s3 rm s3://mybucket/ --recursive --exclude "*.jpg"

Output::

    delete: myDir/test1.txt to s3://mybucket/test1.txt

The following ``rm`` command recursively deletes all objects under a specified bucket and prefix when passed with the
parameter ``--recursive`` while excluding all objects under a particular prefix by using an ``--exclude`` parameter.  In
this example, the bucket ``mybucket`` has the objects ``test1.txt`` and ``another/test.txt``::

    aws s3 rm s3://mybucket/ --recursive --exclude "mybucket/another/*"

Output::

    delete: myDir/test1.txt to s3://mybucket/test1.txt


.. _Use of Exclude and Include Filters: http://docs.aws.amazon.com/cli/latest/reference/s3/index.html#use-of-exclude-and-include-filters
