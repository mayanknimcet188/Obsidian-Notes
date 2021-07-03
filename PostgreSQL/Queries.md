### Basic SQL Queries
```
CREATE TABLE cities (
  name VARCHAR(50),
  country VARCHAR(50),
  population INTEGER,
  area INTEGER
  );
```

```
INSERT INTO cities (name, country, population,area)
VALUES ('Tokyo','Japan',38505000,8223),
('Delhi','India',28125000,2240),
('Shanghai','China',22125000,4015),
('Sao Paulo','Brazil',20935000,3043);
```

```
UPDATE cities
SET population = 39505000
WHERE name = 'Tokyo';
```

```
DELETE FROM cities WHERE name = 'Tokyo';
```

```
INSERT INTO cities (name,country, population, area)
VALUES ('Tokyo','Japan',38505000,8223);
```

### Working with tables
Database for a photo sharing app

**Users table**
```
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  username VARCHAR(50)
  );
```

```
INSERT INTO
  users (username)
VALUES
  ('monahan93'),('pfferer'),('si93onis'),('99stroman');
```

**Photos table**
```
CREATE table photos (
	id SERIAL PRIMARY KEY,
  url VARCHAR(200),
  user_id INTEGER REFERENCES users(id)
);
```

```
INSERT INTO photos (url,user_id) 
VALUES ('https://one.jpg',4);
```

```
INSERT INTO photos (url,user_id)
VALUES ('http://two.jpg',1),
('http://23.jpg',1),
('http://43.jpg',1),
('http://25.jpg',2),
('http://54.jpg',3),
('http://256.jpg',4);
```

```
SELECT * FROM photos WHERE user_id = 4;
```

```

```