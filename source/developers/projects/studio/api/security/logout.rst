.. _crafter-studio-api-security-logout:

======
Logout
======

Logouts the current user.

--------------------
Resource Information
--------------------

+----------------------------+-------------------------------------------------------------------+
|| HTTP Verb                 || POST                                                             |
+----------------------------+-------------------------------------------------------------------+
|| URL                       || ``/api/1/services/api/1/security/logout.json``                   |
+----------------------------+-------------------------------------------------------------------+
|| Response Formats          || ``JSON``                                                         |
+----------------------------+-------------------------------------------------------------------+

----------
Parameters
----------

None

-------
Example
-------

^^^^^^^
Request
^^^^^^^

``POST .../api/1/services/api/1/security/logout.json``

^^^^^^^^
Response
^^^^^^^^

``Status 200 OK``

---------
Responses
---------

+---------+-------------------------------------------+---------------------------------------------------+
|| Status || Location                                 || Response Body                                    |
+=========+===========================================+===================================================+
|| 200    ||                                          || ``{ "message" : "OK" }``                         |
+---------+-------------------------------------------+---------------------------------------------------+
|| 500    ||                                          || ``{ "message" : "Internal server error.``        |
||        ||                                          || ``ACTUAL_EXCEPTION" }``                          |
+---------+-------------------------------------------+---------------------------------------------------+
