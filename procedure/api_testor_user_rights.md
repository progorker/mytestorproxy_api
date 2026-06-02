```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
 [procedure] api_testor_user_rights
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_user_rights (
  in p_token varchar(36), 
  out p_api_call int,
  out p_user_make int,
  out p_user_demo int,
  out p_storage_full int
)


-------|__/-------------------------
               USAGE
------------------------------------

$) set @v_token = '_'; call mytestorproxy.api_testor_login( @v_token, 'mytestor', 'rzutomqahegpnyx' ); select @v_token;

    ----------------------------

+----------------------------------+
| @v_token                         |
+----------------------------------+
| 52a49370db50e54c02ec8956b981fab4 |
+----------------------------------+

    ----------------------------

$) set @v_api_call = -1; set @v_user_make = -1; set @v_user_demo = -1; set @v_storage_full = -1; call mytestorproxy.api_testor_user_rights( '52a49370db50e54c02ec8956b981fab4', @v_api_call, @v_user_make, @v_user_demo, @v_storage_full ); select @v_api_call, @v_user_make, @v_user_demo, @v_storage_full;

    ----------------------------

+-------------+--------------+--------------+-----------------+
| @v_api_call | @v_user_make | @v_user_demo | @v_storage_full |
+-------------+--------------+--------------+-----------------+
|           1 |            0 |            1 |               0 |
+-------------+--------------+--------------+-----------------+

    ----------------------------


```
