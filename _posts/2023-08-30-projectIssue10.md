---
title: "JPA 쿼리 메서드"
excerpt: "예약 비즈니스 로직 처리에 활용할 데이터 조회를 위한 JPA 쿼리 메서드"

categories:
  - Project
tags:
  - [tag1, tag2]

permalink: /project/projectIssue10/

toc: true
toc_sticky: true

date: 2023-08-30
last_modified_at: 2023-08-30
---

## 🔎 본문

### JPA 쿼리 메서드가 뭘까? 
- JPA는 ORM(Object-Relation Mapping) 기술을 구현한 것이고, 데이터베이스의 테이블을 **자바 객체**로 매핑하여
데이터를 조작하는 작업을 간편하게 처리할 수 있다
- 데이터베이스 SQL 구문과 같이 쿼리를 직접 작성하지 않고도 자바 메서드 이름 규칙을 따라 간단한 메서드 선언으로
원하는 데이터를 추출할 수 있다.

### 프로젝트 내 예약 기능에서 사용한 JPA 쿼리 메서드
- 멤버(A)가 구장(B)를 예약 했다고 가정했을 때, 멤버(A)가 구장(B)을 중복으로 예약되는 것을 방지해야 했다.
- 그래서, 멤버의 ID와 예약 가능한 구장의 ID가 이미 존재하는지를 확인하기 위해서
**'existByMemberIdAndReservableStadiumId'** 라는 쿼리 메서드를 정의하여 처리