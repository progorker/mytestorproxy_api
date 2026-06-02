```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
   [procedure] api_testor_source
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_source (
  in p_token varchar(36),
  in p_suite_id bigint,
  in p_case_code varchar(768)
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

$) set @v_data = '/src/table/table_users.sql'; call mytestorproxy.api_testor_option( '8003c6c90940e847a8e01897b4a93e4d', 1, @v_data, 'src:table_users', false ); set @v_data = null; call mytestorproxy.api_testor_option( '8003c6c90940e847a8e01897b4a93e4d', 1, @v_data, 'src:table_users', false ); select @v_data;

    ----------------------------

+----------------------------+
| @v_data                    |
+----------------------------+
| /src/table/table_users.sql |
+----------------------------+

    ----------------------------

$) call mytestorproxy.api_testor_source( '8003c6c90940e847a8e01897b4a93e4d', 1, 'table_users' );

    ----------------------------

+----------+--------------------------------------------------+
| Key      | Value                                            |
+----------+--------------------------------------------------+
| Case     | table_users                                      |
| Relative | /src/table/table_users.sql                       |
| Absolute | /bioogr/works/mysterry/src/table/table_users.sql |
| Root     | /bioogr/works/mysterry                           |
+----------+--------------------------------------------------+

    ----------------------------

```
