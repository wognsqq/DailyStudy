## DATABASE2 MySQL - 6.��Ű���� ���
# schema, mySQL ���� �����ͺ��̽��� ����� ����.
 - mysql create database ���ۿ� �˻�
 - mysql> CREATE DATABASE menagerie;
 -  create database oxox; Query OK, 1 row affected (0.00 sec)
 - �߿��Ѱ� �˻��� ���ؼ� �˾Ƴ��� �ȴ�. 
 - how to show database list in mysql�˻� ����
 - SHOW DATABASES;
 - mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| oxox               |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)
 - �� ������ ���̽��� ����ϰڴ� =>USE
 - mysql> USE oxox;
Database changed
 - ������ ���̽� �������� �߰� ǥ�� �ٷﺾ�ô�.

## DATABASE2 MYSQL - 7. SQL�� ���̺��� ����
# �����ͺ��̽��� ��û���� ���� �����͸� �ٷ�� ������, �������� �����غ��ڱ�
 - SQL (Structured Query Language)
 - ������ �����ͺ��̽��� ǥ�� ���� S
 - �����͸� �־���, �о���, ���� ���� ��Ű���� �������, ��û�ϴ� �����ϴ�=>����,Q
 - �����ͺ��̽��� ������ �� �ְ� ���� ������ �� �ִ� ��� => Language
### SQL ��ǻ�� ����� Ư¡  
 - � ��ǻ�� ���� ����. (HTML, SQL �Ѵ� ����.)
 - ���� �߿��ϴ�. SQL�� ������ �����ͺ��̽���� ī�װ� ���� ��ǰ���� ���������� �����ͺ��̽��� ������ �� ����ϴ�, ǥ��ȭ�� ���.
 - ǥ�� ���������� �ٷﺸ��.
 - ǥ: table, x��� y������ �ɰ��� ������ �� �ִµ� 
 - x��(����) - row , record, �� , =>row�� ������ �ϳ��ϳ�, ������ ��ü
 - y��(����) - column, �� =>�÷��� ����� ���� data�� Ÿ��, �������� ����
 - �����͸� ����� �߰� ���� �ϰ� �غ��ô�.

## DATABASE2 MYSQL - 8.1 ���̺��� ����
# ���̺� ���� �غ���.
 - create table in mysql cheat sheet �˻�
 - mysql�α��� 
 - �������� ��Ʈ�� �÷��� � ������ �����͸� ���� �� �ִ�. �����ͺ��̽������� , �ݵ�� ���ڷ� ���;��Ѵ�. ��¥�� ���;� �Ѵٸ� ������ �� �� �ִ�. (�����Ͱ� �ſ� �����ϱ�)
 - ����: �÷��� ������ Ÿ���� ������ �� �ִ�.  ���� �� �Ű� �� �ʿ䰡 ����. (�ݵ�� id�� ���ڴ�. �ݵ�� created �÷��� �ð��̴�...)
 - mysql datatype number �˻� (�÷����� ������ �Է°��� �����ϱ� ����)
 - �ִ��� �ڽ��� �����Ϸ��� �ϴ� �����Ϳ� �ִ밪�� ���� ����� ������ Ÿ�� ������ ����ȭ.
 - not null ( ���� ���� ���� ������� �ʰڴ�.)
 - 3��° ���� �����϶�� �ϸ�, ���� ������ �÷��� ���� ������ ���� �ִٸ�? id���� 3�� ���� ������. 
 - �����͸� �߰��� ��, ������ ���̵𺸴� +1�� ���� �Է��ϸ�=> �ڵ� auto ���� increment
 mysql> use oxox
Database changed
mysql>
mysql>
mysql>
mysql>
mysql>
mysql>
mysql>
mysql>
mysql> create table topic(
    ->  id int(11) not null auto_increment,
=> �� �÷��� �������...
 - 
 
