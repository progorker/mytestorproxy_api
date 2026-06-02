```
===========_____=======_============
  _ __ _  |_   _|__ __| |_ ___ _ _ 
 | '  \ || || |/ -_|_-<  _/ _ \ '_|
 |_|_|_\_, ||_|\___/__/\__\___/_|  
=======|__/=========================
  API References of myTestorProxy
           ----- oOo -----
    [procedure] api_testor_error
====================================


-------|__/-------------------------
               SYNTAX
------------------------------------

procedure mytestorproxy.api_testor_error (
  in p_token varchar(36),
  out p_id bigint,
  in p_suite_id bigint,
  in p_case_id bigint,
  in p_code varchar(640),
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
| 8003c6c90940e847a8e01897b4a93e4d |
+----------------------------------+

    ----------------------------

$) call mytestorproxy.api_testor_clean( '8003c6c90940e847a8e01897b4a93e4d', 1 );

$) set @v_case_id = -1; set @v_suite_id = -1; call mytestorproxy.api_testor_suite_case( '8003c6c90940e847a8e01897b4a93e4d', @v_suite_id, @v_case_id, 'sterry', 'table-users' ); select @v_case_id, @v_suite_id;

    ----------------------------

+------------+-------------+
| @v_case_id | @v_suite_id |
+------------+-------------+
|          4 |           1 |
+------------+-------------+

    ----------------------------

$) set @v_test_id = -1; set @v_suite_id = 1; set @v_case_id = 4; call mytestorproxy.api_testor_error( '8003c6c90940e847a8e01897b4a93e4d', @v_test_id, @v_suite_id, @v_case_id, 'exception.1', 'Field is missing!' ); select @v_test_id, @v_suite_id, @v_case_id;

    ----------------------------

+------------+-------------+------------+
| @v_test_id | @v_suite_id | @v_case_id |
+------------+-------------+------------+
|          6 |           1 |          4 |
+------------+-------------+------------+

    ----------------------------

$) call mytestorproxy.api_testor_finish( '8003c6c90940e847a8e01897b4a93e4d', 1 );

    ----------------------------

+-------------+-------------+--------------------------------------------------------------------+
| case        | test        | message                                                            |
+-------------+-------------+--------------------------------------------------------------------+
| table-users | exception.1 | [exception.1] test (error) is failed. 
Message: Field is missing!
 |
+-------------+-------------+--------------------------------------------------------------------+
1 row in set (0.28 sec)

+---------+--------+--------+----+---------------+--------------+------------+------------+
| version | status | code   | id | success_count | failed_count | test_count | case_count |
+---------+--------+--------+----+---------------+--------------+------------+------------+
|      18 | RED    | sterry |  1 |             0 |            1 |          1 |          1 |
+---------+--------+--------+----+---------------+--------------+------------+------------+
1 row in set (0.28 sec)

+------------------------------------------+-----------------------------------------------+
| To re-print:                             | To get source file of [a] test case:          |
+------------------------------------------+-----------------------------------------------+
| $) call api_testor_result('_token_', 1); | $) call api_testor_source('_token_', 1, 'a'); |
+------------------------------------------+-----------------------------------------------+
1 row in set (0.28 sec)

    ----------------------------

```
