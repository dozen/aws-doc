[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs delete-file-system:


******************
delete-file-system
******************



===========
Description
===========



Deletes a file system, permanently severing access to its contents. Upon return, the file system no longer exists and you will not be able to access any contents of the deleted file system. 

 

You cannot delete a file system that is in use. That is, if the file system has any mount targets, you must first delete them. For more information, see  describe-mount-targets and  delete-mount-target . 

 

.. note::

  The ``delete-file-system`` call returns while the file system state is still "deleting". You can check the file system deletion status by calling the  describe-file-systems API, which returns a list of file systems in your account. If you pass file system ID or creation token for the deleted file system, the  describe-file-systems will return a 404 "FileSystemNotFound" error.

 

This operation requires permission for the ``elasticfilesystem:DeleteFileSystem`` action.



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.efs true`` 



========
Synopsis
========

::

    delete-file-system
  --file-system-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--file-system-id`` (string)


  The ID of the file system you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None