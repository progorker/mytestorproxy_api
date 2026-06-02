```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
   [procedure] api_testor_option
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_option (
  in p_token varchar(36),
  in p_suite_id bigint,
  inout p_data varchar(8192),
  in p_code varchar(768),
  in p_remove int
)

-------|__/-------------------------
               USAGE
------------------------------------

$) set @v_token = '_'; call mytestorproxy.api_testor_login( @v_token, 'mytestor', 'rzutomqahegpnyx' ); select @v_token;

    ----------------------------

+----------------------------------+
| @v_token                         |
+----------------------------------+
| 8003c6c90940e847a8e01897b4a93e4d |
+----------------------------------+

    ----------------------------

$) set @v_case_id = -1; set @v_suite_id = -1; call mytestorproxy.api_testor_suite_case( '8003c6c90940e847a8e01897b4a93e4d', @v_suite_id, @v_case_id, 'sterry', 'table-users' ); select @v_case_id, @v_suite_id;

    ----------------------------

+------------+-------------+
| @v_case_id | @v_suite_id |
+------------+-------------+
|          1 |           1 |
+------------+-------------+

    ----------------------------

$) set @v_data = '/bioogr/works/mysterry'; call mytestorproxy.api_testor_option( '8003c6c90940e847a8e01897b4a93e4d', 1, @v_data, 'src_dir', false ); set @v_data = null; call mytestorproxy.api_testor_option( '8003c6c90940e847a8e01897b4a93e4d', 1, @v_data, 'src_dir', false ); select @v_data;

    ----------------------------

+------------------------+
| @v_data                |
+------------------------+
| /bioogr/works/mysterry |
+------------------------+

    ----------------------------


```
