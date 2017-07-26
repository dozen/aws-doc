[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-instance-profile:


***********************
delete-instance-profile
***********************



===========
Description
===========



Deletes the specified instance profile. The instance profile must not have an associated role.

 

.. warning::

   

  Make sure you do not have any Amazon EC2 instances running with the instance profile you are about to delete. Deleting a role or instance profile that is associated with a running instance will break any applications running on the instance.

   

 

For more information about instance profiles, go to `About Instance Profiles <http://docs.aws.amazon.com/IAM/latest/UserGuide/AboutInstanceProfiles.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/DeleteInstanceProfile>`_


========
Synopsis
========

::

    delete-instance-profile
  --instance-profile-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-profile-name`` (string)


  The name of the instance profile to delete.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an instance profile**

The following ``delete-instance-profile`` command deletes the instance profile named ``ExampleInstanceProfile``::

  aws iam delete-instance-profile --instance-profile-name ExampleInstanceProfile

For more information, see `Instance Profiles`_ in the *Using IAM* guide.

.. _`Instance Profiles`: http://docs.aws.amazon.com/IAM/latest/UserGuide/instance-profiles.html



======
Output
======

None