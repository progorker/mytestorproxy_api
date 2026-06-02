```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
[procedure] api_testor_current_user
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_current_user ( 
  in p_token varchar(36),
  out p_user_id bigint,
  out p_username varchar(1024)
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

$) set @v_user_id = -1; set @v_username = '_'; call mytestorproxy.api_testor_current_user( '52a49370db50e54c02ec8956b981fab4', @v_user_id, @v_username ); select @v_user_id, @v_username;

    ----------------------------

+------------+-------------+
| @v_user_id | @v_username |
+------------+-------------+
|          2 | mytestor    |
+------------+-------------+

    ----------------------------


```
