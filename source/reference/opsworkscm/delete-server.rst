[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm delete-server:


*************
delete-server
*************



===========
Description
===========



Deletes the server and the underlying AWS CloudFormation stack (including the server's EC2 instance). When you run this command, the server state is updated to ``DELETING`` . After the server is deleted, it is no longer returned by ``DescribeServer`` requests. If the AWS CloudFormation stack cannot be deleted, the server cannot be deleted. 

 

This operation is asynchronous. 

 

An ``InvalidStateException`` is thrown when a server deletion is already in progress. A ``ResourceNotFoundException`` is thrown when the server does not exist. A ``ValidationException`` is raised when parameters of the request are not valid. 

 

 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/DeleteServer>`_


========
Synopsis
========

::

    delete-server
  --server-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--server-name`` (string)


  The ID of the server to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete servers**

The following ``delete-server`` command deletes a Chef Automate server, identified
by the server's name. After the server is deleted, it is no longer returned by
``DescribeServer`` requests.::

  aws opsworks-cm delete-server --server-name "automate-06"

The output shows whether the server deletion succeeded.

**More Information**

For more information, see `Delete an AWS OpsWorks for Chef Automate Server`_ in the *AWS OpsWorks User Guide*.

.. _`Delete an AWS OpsWorks for Chef Automate Server`: http://docs.aws.amazon.com/opsworks/latest/userguide/opscm-delete-server.html



======
Output
======

