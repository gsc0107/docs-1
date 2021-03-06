.. _crafter-studio-api-user-reset-password:

==============
Reset Password
==============

Allow the administrator to reset Crafter Studio's user password provided.

--------------------
Resource Information
--------------------

+----------------------------+-------------------------------------------------------------------+
|| HTTP Verb                 || POST                                                             |
+----------------------------+-------------------------------------------------------------------+
|| URL                       || ``/api/1/services/api/1/user/reset-password.json``               |
+----------------------------+-------------------------------------------------------------------+
|| Response Formats          || ``JSON``                                                         |
+----------------------------+-------------------------------------------------------------------+
|| Required Role             || Admin                                                            |
+----------------------------+-------------------------------------------------------------------+

----------
Parameters
----------

+---------------+-------------+---------------+--------------------------------------------------+
|| Name         || Type       || Required     || Description                                     |
+===============+=============+===============+==================================================+
|| username     || String     || |checkmark|  || Username to use                                 |
+---------------+-------------+---------------+--------------------------------------------------+
|| new          || String     ||              || User's new password (clear)                     |
+---------------+-------------+---------------+--------------------------------------------------+

-------
Example
-------

.. code-block:: guess

	POST .../api/1/services/api/1/user/reset-password.json

.. code-block:: json

  {
    "username" : "jane.doe",
    "new" : "SuperSecretPassword321#"
  }

--------
Response
--------

+---------+-------------------------------------------+---------------------------------------------------+
|| Status || Location                                 || Response Body                                    |
+=========+===========================================+===================================================+
|| 200    || ``.../user/get.json?username=:username`` || ``{ "message" : "OK" }``                         |
+---------+-------------------------------------------+---------------------------------------------------+
|| 400    ||                                          || ``{ "message" : "Invalid parameter(s)" }``       |
+---------+-------------------------------------------+---------------------------------------------------+
|| 400    ||                                          || ``{ "message" : "Bad Request" }``                |
+---------+-------------------------------------------+---------------------------------------------------+
|| 401    ||                                          || ``{ "message" : "Unauthorized" }``               |
+---------+-------------------------------------------+---------------------------------------------------+
|| 403    ||                                          || ``{ "message" : "Externally managed user" }``    |
+---------+-------------------------------------------+---------------------------------------------------+
|| 404    ||                                          || ``{ "message" : "User not found" }``             |
+---------+-------------------------------------------+---------------------------------------------------+
|| 500    ||                                          || ``{ "message" : "Internal server error" }``      |
+---------+-------------------------------------------+---------------------------------------------------+
