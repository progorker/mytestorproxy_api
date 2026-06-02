```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
  [procedure] api_testor_e_tables
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_e_tables (
  in p_mysql_database varchar(8192),
  in p_find varchar(8192),
  out p_names mediumtext
)


-------|__/-------------------------
               USAGE
------------------------------------

$) SET SESSION sql_require_primary_key = OFF;

$) set @v_names = '_'; call mytestorproxy.api_testor_e_tables( 'mytestor', '', @v_names ); select @v_names;

    ----------------------------

+----------------+
| @v_names       |
+----------------+
| testor_welcome |
+----------------+

    ----------------------------

```
