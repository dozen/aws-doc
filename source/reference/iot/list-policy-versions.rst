[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-policy-versions:


********************
list-policy-versions
********************



===========
Description
===========



Lists the versions of the specified policy, and identifies the default version.



========
Synopsis
========

::

    list-policy-versions
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-name`` (string)


  The policy name.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

policyVersions -> (list)

  

  The policy versions.

  

  (structure)

    

    Describes a policy version.

    

    versionId -> (string)

      

      The policy version ID.

      

      

    isDefaultVersion -> (boolean)

      

      Specifies whether the policy version is the default.

      

      

    createDate -> (timestamp)

      

      The date and time the policy was created.

      

      

    

  

