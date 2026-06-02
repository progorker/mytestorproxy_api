```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
    [procedure] api_testor_man
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_man (
  in p_module varchar(64),
  in p_kind varchar(36),
  in p_code varchar(640),
  out p_man longtext
)


    ----------------------------
             p_module
    ----------------------------

+ 'mytestor'
+ 'mytestorproxy'


    ----------------------------
              p_kind
    ----------------------------

+ 'table'
+ 'function'
+ 'procedure'


-------|__/-------------------------
               USAGE
------------------------------------


$) set @v_man = '_'; call mytestorproxy.api_testor_man( 'mytestor', 'table', 'testor_welcome', @v_man ); select @v_man as `manual`\G

    ----------------------------

*************************** 1. row ***************************
manual: 
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '   || || |/ -_|_-<  _/ _  '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
     API References of myTestor
           ----- oOo -----
       [table] testor_welcome
====================================


-------|__/-------------------------
               USAGE
------------------------------------

$) select message from testor_welcome order by id asc;

    ----------------------------

+----------------------------------------+
| message                                |
+----------------------------------------+
| Welcome to myTestor 0.0.1!             |
| There are 6 published API procedures:  |
| proc: api_testor_current_user          |
| proc: api_testor_login                 |
| proc: api_testor_logout                |
| proc: api_testor_user_rights           |
| proc: api_testor_create_user           |
| proc: api_testor_change_password       |
| There are 2 published API functions:   |
| func: api_testor_has_right             |
| func: api_testor_is_online             |
+----------------------------------------+

    ----------------------------

    ----------------------------
```
