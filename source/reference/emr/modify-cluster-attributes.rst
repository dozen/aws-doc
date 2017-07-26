[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr modify-cluster-attributes:


*************************
modify-cluster-attributes
*************************



===========
Description
===========

Modifies the cluster attributes 'visible-to-all-users' and 'termination-protected'.



========
Synopsis
========

::

    modify-cluster-attributes
  --cluster-id <value>
  [--visible-to-all-users | --no-visible-to-all-users]
  [--termination-protected | --no-termination-protected]




=======
Options
=======

``--cluster-id`` (string)


  A unique string that identifies the cluster. This identifier is returned by ``create-cluster`` and can also be obtained from ``list-clusters`` .

  

``--visible-to-all-users`` | ``--no-visible-to-all-users`` (boolean)
Change cluster visibility for IAM users

``--termination-protected`` | ``--no-termination-protected`` (boolean)
Set termination protection on or off



========
Examples
========

The following command sets the visibility of an EMR cluster with the ID ``j-301CDNY0J5XM4`` to all users::

  aws emr modify-cluster-attributes --cluster-id j-301CDNY0J5XM4 --visible-to-all-users
