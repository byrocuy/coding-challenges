```sql
CREATE TABLE employee (
  `employee_id` INTEGER,
  `name` VARCHAR(8),
  `months` INTEGER,
  `salary` INTEGER
);

INSERT INTO employee
  (`employee_id`, `name`, `months`, `salary`)
VALUES
  ('12228', 'rose', '15', '1968'),
  ('33645', 'angela', '1', '3443'),
  ('45692', 'frank', '17', '1608'),
  ('56118', 'patrick', '7', '1345'),
  ('59725', 'lisa', '11', '2330'),
  ('74197', 'kimberly', '16', '4372'),
  ('78454', 'bonnie', '8', '1771'),
  ('83565', 'michael', '6', '2017'),
  ('98607', 'todd', '5', '3396'),
  ('99989', 'joe', '9', '3573');
```