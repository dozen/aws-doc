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



========
Synopsis
========

::

    delete-configuration-template
  --application-name <value>
  --template-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of the application to delete the configuration template from. 

  

``--template-name`` (string)


  The name of the configuration template to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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