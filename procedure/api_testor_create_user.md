```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
 [procedure] api_testor_create_user
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_create_user (
  in p_token varchar(36), 
  in p_username varchar(1024),
  in p_password varchar(4096),
  in p_api_call int,
  in p_user_make int,
  in p_user_demo int,
  in p_quota bigint
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

$) call mytestorproxy.api_testor_create_user( '52a49370db50e54c02ec8956b981fab4', 'demo', 'homosapien', 1, 0, 1, 1024 * 1024 * 768 );


```
