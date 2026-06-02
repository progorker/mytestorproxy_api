```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
 [procedure] api_testor_has_right
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_has_right (
  in p_token varchar(36),
  in p_right_code varchar(64),
  out p_result int
)


    ----------------------------
           p_right_code
    ----------------------------

+ 'api_call'
+ 'user_make'
+ 'user_demo'
+ 'storage_full'

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

$) set @v_right = -1; call mytestorproxy.api_testor_has_right( '52a49370db50e54c02ec8956b981fab4', 'api_call', @v_right ); select @v_right;

    ----------------------------

+----------+
| @v_right |
+----------+
|        1 |
+----------+

    ----------------------------

```
