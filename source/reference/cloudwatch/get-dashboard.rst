[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch get-dashboard:


*************
get-dashboard
*************



===========
Description
===========



Displays the details of the dashboard that you specify.

 

To copy an existing dashboard, use ``get-dashboard`` , and then use the data returned within ``DashboardBody`` as the template for the new dashboard when you call ``put-dashboard`` to create the copy.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/GetDashboard>`_


========
Synopsis
========

::

    get-dashboard
  [--dashboard-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dashboard-name`` (string)


  The name of the dashboard to be described.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DashboardArn -> (string)

  

  The Amazon Resource Name (ARN) of the dashboard.

  

  

DashboardBody -> (string)

  

  The detailed information about the dashboard, including what widgets are included and their location on the dashboard. For more information about the ``DashboardBody`` syntax, see  CloudWatch-Dashboard-Body-Structure . 

  

  

DashboardName -> (string)

  

  The name of the dashboard.

  

  

