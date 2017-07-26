[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk delete-configuration-template:


*****************************
delete-configuration-template
*****************************



===========
Description
===========



Deletes the specified configuration template.

 

.. note::

   

  When you launch an environment using a configuration template, the environment gets a copy of the template. You can delete or modify the environment's copy of the template without affecting the running environment.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DeleteConfigurationTemplate>`_


========
Synopsis
========

::

    delete-configuration-template
  --application-name <value>
  --template-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application to delete the configuration template from.

  

``--template-name`` (string)


  The name of the configuration template to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a configuration template**

The following command deletes a configuration template named ``my-template`` for an application named ``my-app``::

  aws elasticbeanstalk delete-configuration-template --template-name my-template --application-name my-app


======
Output
======

None