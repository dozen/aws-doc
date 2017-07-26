[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch put-dashboard:


*************
put-dashboard
*************



===========
Description
===========



Creates a dashboard if it does not already exist, or updates an existing dashboard. If you update a dashboard, the entire contents are replaced with what you specify here.

 

You can have up to 500 dashboards per account. All dashboards in your account are global, not region-specific.

 

To copy an existing dashboard, use ``get-dashboard`` , and then use the data returned within ``dashboard-body`` as the template for the new dashboard when you call ``put-dashboard`` to create the copy.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/PutDashboard>`_


========
Synopsis
========

::

    put-dashboard
  [--dashboard-name <value>]
  [--dashboard-body <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dashboard-name`` (string)


  The name of the dashboard. If a dashboard with this name already exists, this call modifies that dashboard, replacing its current contents. Otherwise, a new dashboard is created. The maximum length is 255, and valid characters are A-Z, a-z, 0-9, ".", "-", and "_".

  

``--dashboard-body`` (string)


  The detailed information about the dashboard in JSON format, including the widgets to include and their location on the dashboard.

   

  For more information about the syntax, see  CloudWatch-Dashboard-Body-Structure .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DashboardValidationMessages -> (list)

  

  If the input for ``put-dashboard`` was correct and the dashboard was successfully created or modified, this result is empty.

   

  If this result includes only warning messages, then the input was valid enough for the dashboard to be created or modified, but some elements of the dashboard may not render.

   

  If this result includes error messages, the input was not valid and the operation failed.

  

  (structure)

    

    An error or warning for the operation.

    

    DataPath -> (string)

      

      The data path related to the message.

      

      

    Message -> (string)

      

      A message describing the error or warning.

      

      

    

  

