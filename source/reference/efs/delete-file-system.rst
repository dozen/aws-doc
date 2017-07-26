[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs delete-file-system:


******************
delete-file-system
******************



===========
Description
===========



Deletes a file system, permanently severing access to its contents. Upon return, the file system no longer exists and you can't access any contents of the deleted file system.

 

You can't delete a file system that is in use. That is, if the file system has any mount targets, you must first delete them. For more information, see  describe-mount-targets and  delete-mount-target . 

 

.. note::

   

  The ``delete-file-system`` call returns while the file system state is still ``deleting`` . You can check the file system deletion status by calling the  describe-file-systems operation, which returns a list of file systems in your account. If you pass file system ID or creation token for the deleted file system, the  describe-file-systems returns a ``404 FileSystemNotFound`` error.

   

 

This operation requires permissions for the ``elasticfilesystem:DeleteFileSystem`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticfilesystem-2015-02-01/DeleteFileSystem>`_


========
Synopsis
========

::

    delete-file-system
  --file-system-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--file-system-id`` (string)


  ID of the file system you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None