[ :ref:`aws <cli:aws>` ]

.. _cli:aws codestar:


********
codestar
********



===========
Description
===========

 

This is the API reference for AWS CodeStar. This reference provides descriptions of the operations and data types for the AWS CodeStar API along with usage examples.

 

You can use the AWS CodeStar API to work with:

 

Projects and their resources, by calling the following:

 

 
*  delete-project , which deletes a project in AWS CodeStar. 
 
*  describe-project , which lists the attributes of a project. 
 
*  list-projects , which lists all AWS CodeStar projects associated with your AWS account. 
 
*  list-resources , which lists the resources associated with an AWS CodeStar project. 
 
*  update-project , which updates the attributes of an AWS CodeStar project. 
 

 

Teams and team members, by calling the following:

 

 
*  associate-team-member , which adds an IAM user to the team for an AWS CodeStar project. 
 
*  disassociate-team-member , which removes an IAM user from the team for an AWS CodeStar project. 
 
*  list-team-members , which lists all the IAM users in the team for an AWS CodeStar project, including their roles and attributes. 
 

 

Users, by calling the following:

 

 
*  create-user-profile , which creates a user profile that contains data associated with the user across all AWS CodeStar projects. 
 
*  delete-user-profile , which deletes all user profile information across all AWS CodeStar projects. 
 
*  describe-user-profile , which describes the profile of a user. 
 
*  list-user-profiles , which lists all AWS CodeStar user profiles. 
 
*  update-user-profile , which updates the profile for an AWS CodeStar user.  
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  associate-team-member
  create-project
  create-user-profile
  delete-project
  delete-user-profile
  describe-project
  describe-user-profile
  disassociate-team-member
  list-projects
  list-resources
  list-team-members
  list-user-profiles
  update-project
  update-team-member
  update-user-profile
