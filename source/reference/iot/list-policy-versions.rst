[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-policy-versions:


********************
list-policy-versions
********************



===========
Description
===========



Lists the versions of the specified policy and identifies the default version.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/ListPolicyVersions>`_


========
Synopsis
========

::

    list-policy-versions
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-name`` (string)


  The policy name.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    

  

