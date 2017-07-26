[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs delete-tags:


***********
delete-tags
***********



===========
Description
===========



Deletes the specified tags from a file system. If the ``delete-tags`` request includes a tag key that does not exist, Amazon EFS ignores it and doesn't cause an error. For more information about tags and related restrictions, see `Tag Restrictions <http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html>`_ in the *AWS Billing and Cost Management User Guide* .

 

This operation requires permissions for the ``elasticfilesystem:DeleteTags`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticfilesystem-2015-02-01/DeleteTags>`_


========
Synopsis
========

::

    delete-tags
  --file-system-id <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--file-system-id`` (string)


  ID of the file system whose tags you want to delete (String).

  

``--tag-keys`` (list)


  List of tag keys to delete.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None