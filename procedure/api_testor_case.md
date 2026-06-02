```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
   [procedure] api_testor_case
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_case (
  in p_token varchar(36),
  out p_id bigint,
  in p_suite_id bigint,
  in p_code varchar(640)
)

-------|__/-------------------------
               USAGE
------------------------------------

$) set @v_token = '_'; call mytestorproxy.api_testor_login( @v_token, 'mytestor', 'rzutomqahegpnyx' ); select @v_token;

    ----------------------------

+----------------------------------+
| @v_token                         |
+----------------------------------+
| a0f2733d08f13423f076732170be6b92 |
+----------------------------------+

    ----------------------------

$) set @v_suite_id = -1; call mytestorproxy.api_testor_suite( 'a0f2733d08f13423f076732170be6b92', @v_suite_id, 'sterry' ); select @v_suite_id;

    ----------------------------

+-------------+
| @v_suite_id |
+-------------+
|           1 |
+-------------+

    ----------------------------

$) set @v_case_id = -1; set @v_suite_id = 1; call mytestorproxy.api_testor_case( 'a0f2733d08f13423f076732170be6b92', @v_case_id, @v_suite_id, 'table-users' ); select @v_case_id, @v_suite_id;

    ----------------------------

+------------+-------------+
| @v_case_id | @v_suite_id |
+------------+-------------+
|          1 |           1 |
+------------+-------------+

    ----------------------------

```
