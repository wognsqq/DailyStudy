## DATABASE2 MySQL - 11.SELECT
- ��� �����͸� ȭ�鿡 ����ϰ� �ʹ�.
- mysql> SELECT id, title, created, author FROM topic; => �������� ���� �͵��� ������ �ʴ´�.
- WHERE - ������ ���� JAEHOON�� ���� ���� �ʹ�. FROM����
- SELECT id, title, created, author FROM topic WHERE author = 'JAEHOON';
- ORDER BY => ���ı��, mysql> SELECT id, title, created, author FROM topic WHERE author = 'JAEHOON' ORDER BY id DESC;
  (�������κ��� ���� "jaehoon"�� ������ �����͸� descending (��������)���� �����޶�.
- ������Ʈ ��Ʈ�� 65,000���� �����͸� ���� �� �ִµ�, �����ͺ��̽��� 10��� ���� �̾Ƴ� �� �ִµ�, �̶� slct from topic �ϸ� ��ǻ�� ������.
- LIMIT =>mysql> SELECT id, title, created, author FROM topic WHERE author = 'JAEHOON' ORDER BY id DESC LIMIT 2;
  (���ѵ� �͸� �� �� �ְ�)
- ������ �ʿ��� .. CRUD �� Read�� ����.

## DATABASE2 MySQL - 12.UPDATE 
- ������ ��� �ұ�?
- sql update mysql �˻�
- UPDATE topic SET description='ORACLE is...', title='Oracle' where id=2;
  (���� Oracle=> ORACLE�� ������Ʈ, ������ ����Ŭ��, ���̵� 2 ������)
- *where���� ���߸��� ���� ����� ��ģ��...

## DATABASE2 MySQL - 13.DELETE
- SQL delete in mySQL
- DELETE FROM topic WHERE id = 5;
  (id 5��mongoDB�� �����Ѵ�.)
- DELETE �߸��ϸ� �λ��� �ڹٲ��...

## DATABASE2 MySQL - 14.������ ����
- ����innovaion�� ����essence�� ���ɺи�
- essence: Database (CRUD)
- innovation: Relational
- �����̶�� �������� ���ζ�� ���������.....
- ���� �� ���� �е��� RDB�� �� �ٸ� �����ͺ��̽��� ���еǴ°�? => Relaational�� �ǹ̴�?
- ������� ���غ���....