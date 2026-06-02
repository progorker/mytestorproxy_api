```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
[procedure] api_testor_not_contains
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_not_contains (
  in p_token varchar(36),
  out p_id bigint,
  in p_suite_id bigint,
  in p_case_id bigint,
  in p_code varchar(640),
  in p_operand varchar(8192),
  in p_value varchar(8192)
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

$) call mytestorproxy.api_testor_clean( '8003c6c90940e847a8e01897b4a93e4d', 1 );

$) set @v_case_id = -1; set @v_suite_id = -1; call mytestorproxy.api_testor_suite_case( '8003c6c90940e847a8e01897b4a93e4d', @v_suite_id, @v_case_id, 'sterry', 'table-users' ); select @v_case_id, @v_suite_id;

    ----------------------------

+------------+-------------+
| @v_case_id | @v_suite_id |
+------------+-------------+
|         14 |           1 |
+------------+-------------+

    ----------------------------

$) set @v_test_id = -1; set @v_suite_id = 1; set @v_case_id = 14; call mytestorproxy.api_testor_not_contains( '8003c6c90940e847a8e01897b4a93e4d', @v_test_id, @v_suite_id, @v_case_id, 'contains.1', 'Hello world!', 'world' ); select @v_test_id, @v_suite_id, @v_case_id;

    ----------------------------

+------------+-------------+------------+
| @v_test_id | @v_suite_id | @v_case_id |
+------------+-------------+------------+
|         25 |           1 |         14 |
+------------+-------------+------------+

    ----------------------------

$) set @v_test_id = -1; set @v_suite_id = 1; set @v_case_id = 14; call mytestorproxy.api_testor_not_contains( '8003c6c90940e847a8e01897b4a93e4d', @v_test_id, @v_suite_id, @v_case_id, 'contains.2', 'Hello world!', 'worldABC' ); select @v_test_id, @v_suite_id, @v_case_id;

    ----------------------------

+------------+-------------+------------+
| @v_test_id | @v_suite_id | @v_case_id |
+------------+-------------+------------+
|         26 |           1 |         14 |
+------------+-------------+------------+

    ----------------------------

$) call mytestorproxy.api_testor_finish( '8003c6c90940e847a8e01897b4a93e4d', 1 );

    ----------------------------

+-------------+------------+----------------------------------------------------------------------------------+
| case        | test       | message                                                                          |
+-------------+------------+----------------------------------------------------------------------------------+
| table-users | contains.1 | [contains.1] test (not_contains) is failed. 
Operand: Hello world!
Value: world
 |
+-------------+------------+----------------------------------------------------------------------------------+
1 row in set (0.31 sec)

+---------+--------+--------+----+---------------+--------------+------------+------------+
| version | status | code   | id | success_count | failed_count | test_count | case_count |
+---------+--------+--------+----+---------------+--------------+------------+------------+
|      28 | RED    | sterry |  1 |             1 |            1 |          2 |          1 |
+---------+--------+--------+----+---------------+--------------+------------+------------+
1 row in set (0.31 sec)

+------------------------------------------+-----------------------------------------------+
| To re-print:                             | To get source file of [a] test case:          |
+------------------------------------------+-----------------------------------------------+
| $) call api_testor_result('_token_', 1); | $) call api_testor_source('_token_', 1, 'a'); |
+------------------------------------------+-----------------------------------------------+
1 row in set (0.31 sec)

    ----------------------------

$) call mytestorproxy.api_testor_success( '8003c6c90940e847a8e01897b4a93e4d', 1 );

    ----------------------------

+-------------+------------+--------------------------------------------------------------------------------------+
| case        | test       | message                                                                              |
+-------------+------------+--------------------------------------------------------------------------------------+
| table-users | contains.2 | [contains.2] test (not_contains) is success. 
Operand: Hello world!
Value: worldABC
 |
+-------------+------------+--------------------------------------------------------------------------------------+

    ----------------------------

```
