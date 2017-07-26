[ :ref:`aws <cli:aws>` ]

.. _cli:aws codecommit:


**********
codecommit
**********



===========
Description
===========

 

This is the *AWS CodeCommit API Reference* . This reference provides descriptions of the operations and data types for AWS CodeCommit API along with usage examples.

 

You can use the AWS CodeCommit API to work with the following objects:

 

Repositories, by calling the following:

 

 
*  batch-get-repositories , which returns information about one or more repositories associated with your AWS account 
 
*  create-repository , which creates an AWS CodeCommit repository 
 
*  delete-repository , which deletes an AWS CodeCommit repository 
 
*  get-repository , which returns information about a specified repository 
 
*  list-repositories , which lists all AWS CodeCommit repositories associated with your AWS account 
 
*  update-repository-description , which sets or updates the description of the repository 
 
*  update-repository-name , which changes the name of the repository. If you change the name of a repository, no other users of that repository will be able to access it until you send them the new HTTPS or SSH URL to use. 
 

 

Branches, by calling the following:

 

 
*  create-branch , which creates a new branch in a specified repository 
 
*  get-branch , which returns information about a specified branch 
 
*  list-branches , which lists all branches for a specified repository 
 
*  update-default-branch , which changes the default branch for a repository 
 

 

Information about committed code in a repository, by calling the following:

 

 
*  get-blob , which returns the base-64 encoded content of an individual Git blob object within a repository 
 
*  get-commit , which returns information about a commit, including commit messages and author and committer information 
 
*  get-differences , which returns information about the differences in a valid commit specifier (such as a branch, tag, HEAD, commit ID or other fully qualified reference) 
 

 

Triggers, by calling the following:

 

 
*  get-repository-triggers , which returns information about triggers configured for a repository 
 
*  put-repository-triggers , which replaces all triggers for a repository and can be used to create or delete triggers 
 
*  test-repository-triggers , which tests the functionality of a repository trigger by sending data to the trigger target 
 

 

For information about how to use AWS CodeCommit, see the `AWS CodeCommit User Guide <http://docs.aws.amazon.com/codecommit/latest/userguide/welcome.html>`_ .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  batch-get-repositories
  create-branch
  create-repository
  credential-helper/index
  delete-repository
  get-blob
  get-branch
  get-commit
  get-differences
  get-repository
  get-repository-triggers
  list-branches
  list-repositories
  put-repository-triggers
  test-repository-triggers
  update-default-branch
  update-repository-description
  update-repository-name
