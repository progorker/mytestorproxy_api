```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
   [procedure] api_testor_clean
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_clean (
  in p_token varchar(36),
  in p_id bigint
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

$) call mytestorproxy.api_testor_clean( 'a0f2733d08f13423f076732170be6b92', 1 );


```
