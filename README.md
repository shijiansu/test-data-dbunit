# test-data-dbunit

![](https://img.shields.io/badge/language-xxx-blue)
![](https://img.shields.io/badge/technology-xxx,%20xxx-blue)
![](https://img.shields.io/badge/development%20year-2021-orange)

![](https://img.shields.io/github/languages/top/shijiansu/test-data-dbunit)
![](https://img.shields.io/github/languages/count/shijiansu/test-data-dbunit)
![](https://img.shields.io/github/languages/code-size/shijiansu/test-data-dbunit)
![](https://img.shields.io/github/repo-size/shijiansu/test-data-dbunit)
![](https://img.shields.io/github/last-commit/shijiansu/test-data-dbunit?color=red)

## Outline

- dbunit-first-try - examples of dbunit + H2 + Flyway (default folder is resources/db/migration) + Apache Druid + JUnit4 (as default). Understand how to connect to database; export to dataset file; verify tables.
  - Pre-condition, need to prepare the database structure e.g. schema and tables, the tables can be created via,
    - Flyway, etc. database migration tool + embedded database environment;
    - Hibernate auto-ddl = create, with or without Spring + embedded database environment;
    - Existing database server with tables.
  - Key features
    - Wrapper with database connection
    - Import dataset file to database data
    - Export database data to dataset file
    - Verify data
      - 单纯的`DBUnit`, 是通过DBUnit的API, 直接verify其ITable
      - 如果使用`database-rider`, 可通过JPA读取数据, 使用第三方lib(e.g. Assertj), verify对应的Entity
  - Few possible use cases
    - Use DBUnit to unit test on data access layer, e.g. Entity and Repository behaviour
    - Use DBUnit to set up testing data in slicing testing on a controller (saving effort from saving data all the time by JPA Entity)
    - Data import and validation together with `database-rider`
- dbunit-first-try-junit5 -  examples of dbunit + H2 + Flyway + Apache Druid + JUnit5
- dbunit-junit5-springboot2 - examples of dbunit + database-rider (mostly) + Spring Boot2 + Junit5 + H2
  - Refer to <https://github.com/database-rider/database-rider/tree/master/rider-examples/spring-boot-dbunit-sample>
  - @DBRider is with @ExtendWith(DBUnitExtension.class) - to support all annotations for DBUnit
  - @SpringBootTest is with @ExtendWith(SpringExtension.class)

## Execute all tests in repo

`/bin/bash run-repo-test.sh`
