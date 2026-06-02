```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
    [procedure] api_testor_test
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_test (
  in p_token varchar(36),
  out p_id bigint,
  in p_suite_id bigint,
  in p_case_id bigint,
  in p_code varchar(640),
  in p_condition int,
  in p_message mediumtext
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

$) set @v_case_id = -1; set @v_suite_id = -1; call mytestorproxy.api_testor_suite_case( 'a0f2733d08f13423f076732170be6b92', @v_suite_id, @v_case_id, 'sterry', 'table-users' ); select @v_case_id, @v_suite_id;

    ----------------------------

+------------+-------------+
| @v_case_id | @v_suite_id |
+------------+-------------+
|          2 |           1 |
+------------+-------------+

    ----------------------------

$) set @v_test_id = -1; set @v_suite_id = 1; set @v_case_id = 2; call mytestorproxy.api_testor_test( 'a0f2733d08f13423f076732170be6b92', @v_test_id, @v_suite_id, @v_case_id, 'greater.1', 2 > 1, '[greater_than] comparation is success' ); select @v_test_id, @v_suite_id, @v_case_id;

    ----------------------------

+------------+-------------+------------+
| @v_test_id | @v_suite_id | @v_case_id |
+------------+-------------+------------+
|          2 |           1 |          2 |
+------------+-------------+------------+

    ----------------------------

$) set @v_test_id = -1; set @v_suite_id = 1; set @v_case_id = 2; call mytestorproxy.api_testor_test( 'a0f2733d08f13423f076732170be6b92', @v_test_id, @v_suite_id, @v_case_id, 'greater.2', 2 <= 1, '[greater_than] comparation is failed' ); select @v_test_id, @v_suite_id, @v_case_id;

    ----------------------------

+------------+-------------+------------+
| @v_test_id | @v_suite_id | @v_case_id |
+------------+-------------+------------+
|          3 |           1 |          2 |
+------------+-------------+------------+

    ----------------------------

```
