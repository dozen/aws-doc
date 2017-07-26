[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf deprecate-activity-type:


***********************
deprecate-activity-type
***********************



===========
Description
===========



Deprecates the specified *activity type* . After an activity type has been deprecated, you cannot create new tasks of that activity type. Tasks of this type that were scheduled before the type was deprecated will continue to run.

 

.. note::

  This operation is eventually consistent. The results are best effort and may not exactly reflect recent updates and changes.

 

**Access Control** 

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains.
 
* Use an ``Action`` element to allow or deny permission to call this action.
 
* Constrain the following parameters by using a ``Condition`` element with the appropriate keys. 

   
  * ``activityType.name`` : String constraint. The key is ``swf:activityType.name`` .
   
  * ``activityType.version`` : String constraint. The key is ``swf:activityType.version`` .
   

 
 

 

If the caller does not have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's **cause** parameter will be set to OPERATION_NOT_PERMITTED. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .



========
Synopsis
========

::

    deprecate-activity-type
  --domain <value>
  --activity-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain in which the activity type is registered.

  

``--activity-type`` (structure)


  The activity type to deprecate.

  



Shorthand Syntax::

    name=string,version=string




JSON Syntax::

  {
    "name": "string",
    "version": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
