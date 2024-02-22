```sql
CREATE TABLE company (
  `company_code` VARCHAR(2),
  `founder` VARCHAR(8)
);

INSERT INTO company
  (`company_code`, `founder`)
VALUES
  ('c1', 'Monika'),
  ('c2', 'Samantha');

CREATE TABLE lead_manager (
  `lead_code` VARCHAR(3),
  `company_code` VARCHAR(2)
);

INSERT INTO lead_manager
  (`lead_code`, `company_code`)
VALUES
  ('lm1', 'c1'),
  ('lm2', 'c2');

CREATE TABLE senior_manager (
  `senior_code` VARCHAR(3),
  `lead_code` VARCHAR(3),
  `company_code` VARCHAR(2)
);

INSERT INTO senior_manager
  (`senior_code`, `lead_code`, `company_code`)
VALUES
  ('sm1', 'lm1', 'c1'),
  ('sm2', 'lm1', 'c1'),
  ('sm3', 'lm2', 'c2');

CREATE TABLE manager (
  `manager_code` VARCHAR(2),
  `senior_code` VARCHAR(3),
  `lead_code` VARCHAR(3),
  `company_code` VARCHAR(2)
);

INSERT INTO manager
  (`manager_code`, `senior_code`, `lead_code`, `company_code`)
VALUES
  ('m1', 'sm1', 'lm1', 'c1'),
  ('m2', 'sm3', 'lm2', 'c2'),
  ('m3', 'sm3', 'lm2', 'c2');

CREATE TABLE employee (
  `employee_code` VARCHAR(2),
  `manager_code` VARCHAR(2),
  `senior_code` VARCHAR(3),
  `lead_code` VARCHAR(3),
  `company_code` VARCHAR(2)
);

INSERT INTO employee
  (`employee_code`, `manager_code`, `senior_code`, `lead_code`, `company_code`)
VALUES
  ('e1', 'm1', 'sm1', 'lm1', 'c1'),
  ('e2', 'm1', 'sm1', 'lm1', 'c1'),
  ('e3', 'm2', 'sm3', 'lm2', 'c2'),
  ('e4', 'm3', 'sm3', 'lm2', 'c2');
```