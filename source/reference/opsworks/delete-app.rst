[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks delete-app:


**********
delete-app
**********



===========
Description
===========



Deletes a specified app.

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DeleteApp>`_


========
Synopsis
========

::

    delete-app
  --app-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--app-id`` (string)


  The app ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an app**

The following example deletes a specified app, which is identified by its app ID.
You can obtain an app ID by going to the app's details page on the AWS OpsWorks console or by
running the ``describe-apps`` command. ::

  aws opsworks delete-app --region us-east-1 --app-id 577943b9-2ec1-4baf-a7bf-1d347601edc5

*Output*: None.

**More Information**

For more information, see `Apps`_ in the *AWS OpsWorks User Guide*.

.. _`Apps`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps.html




======
Output
======

None