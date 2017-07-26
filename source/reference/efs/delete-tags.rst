[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs delete-tags:


***********
delete-tags
***********



===========
Description
===========



Deletes the specified tags from a file system. If the ``delete-tags`` request includes a tag key that does not exist, Amazon EFS ignores it; it is not an error. For more information about tags and related restrictions, go to `Tag Restrictions`_ in the *AWS Billing and Cost Management User Guide* .

 

This operation requires permission for the ``elasticfilesystem:DeleteTags`` action.



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.efs true`` 



========
Synopsis
========

::

    delete-tags
  --file-system-id <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--file-system-id`` (string)


  String. The ID of the file system whose tags you want to delete.

  

``--tag-keys`` (list)


  A list of tag keys to delete.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Tag Restrictions: http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html
