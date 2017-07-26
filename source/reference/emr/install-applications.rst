[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr install-applications:


********************
install-applications
********************



===========
Description
===========

Installs applications on a running cluster. Currently only Hive and Pig can be installed using this command, and this command is only supported by AMI versions (3.x and 2.x).



========
Synopsis
========

::

    install-applications
  --cluster-id <value>
  --applications <value> [<value>...]




=======
Options
=======

``--cluster-id`` (string)


  A unique string that identifies the cluster. This identifier is returned by ``create-cluster`` and can also be obtained from ``list-clusters`` .

  

``--applications`` (list)


  The applications to be installed. Takes the following parameters: ``Name`` and ``Args`` .

  



Shorthand Syntax::

    Args=string,string,Name=string ...




JSON Syntax::

  [
    {
      "Args": ["string", ...],
      "Name": "MapR"|"HUE"|"HIVE"|"PIG"|"HBASE"|"IMPALA"|"GANGLIA"|"HADOOP"|"SPARK"
    }
    ...
  ]



