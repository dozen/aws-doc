[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` . :ref:`credential-helper <cli:aws codecommit credential-helper>` ]

.. _cli:aws codecommit credential-helper get:


***
get
***



===========
Description
===========

get a username SigV4 credential pair based on protocol, host and path provided from standard in. This is primarily called by git to generate credentials to authenticate against AWS CodeCommit



========
Synopsis
========

::

    aws codecommit credential-helper get




=======
Options
=======

``--ignore-host-check`` (boolean)
Optional. Generate credentials regardless of whether the domain is an Amazon domain.



========
Examples
========

echo -e "protocol=https\\npath=/v1/repos/myrepo\\nhost=git-codecommit.us-east-1.amazonaws.com" | aws codecommit credential-helper get