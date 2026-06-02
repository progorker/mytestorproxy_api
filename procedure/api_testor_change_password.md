```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
[procedure] api_testor_change_password
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_change_password (
  in p_token varchar(36), 
  in p_password varchar(4096)
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

$) call mytestorproxy.api_testor_change_password( '52a49370db50e54c02ec8956b981fab4', 'homosapien' );



```
