```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
 [procedure] api_testor_is_online
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_is_online (
  in p_token varchar(36),
  out p_result int
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

$) set @v_online = -1; call mytestorproxy.api_testor_is_online( '52a49370db50e54c02ec8956b981fab4', @v_online ); select @v_online;

    ----------------------------

+-----------+
| @v_online |
+-----------+
|         1 |
+-----------+

    ----------------------------

```
