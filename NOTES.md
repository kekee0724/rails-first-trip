# Rails vs Spring · 学习笔记（Java 工程师视角）

> 持续更新。约定：左边 Rails，右边 Spring Boot。

## 1. 哲学差异

| Rails | Spring Boot |
|---|---|
| Convention over configuration（目录即路由、命名即约定） | Explicit configuration（注解 + JavaConfig 显式声明） |
| 「魔法」多，但魔法都是约定 | 几乎无魔法，一切可追溯 |

## 2. ORM：ActiveRecord vs JPA/Hibernate

- `has_many / belongs_to` ≈ `@OneToMany / @ManyToOne`，但 AR 把关联写在模型里更直观
- migration ≈ Flyway/Liquibase，但 AR migration 是 Ruby DSL，可回滚（`rails db:rollback`）——比 SQL 脚本优雅
- N+1 问题两边一模一样：Rails 用 `includes`，JPA 用 `JOIN FETCH / @EntityGraph`

## 3. 已遇到的坑

- （学到一个记一个）
