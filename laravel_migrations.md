# Laravel Study

## 마이그레이션 (Migrations)

> ### 참고
> - [라라벨 공식 메뉴얼 (v5.5)](https://laravel.com/docs/5.5/migrations)
> - [라라벨 번역 메뉴얼 (v5.4)](https://laravel.kr/docs/5.4/migrations)

### 소개
- 데이터베이스를 위한 버전 컨트롤 역할
- 데이터베이스 스키마를 제어
- 보통 Schema와 쌍을 이룸


---
#### 제어 명령 (artisan 명령어)

##### 생성하기

```shell
php artisan make:migration [마이그레이션명]
```

> - [라라벨]/database/migrations/[마이그레이션명_타임스템프].php 파일이 생성
> - 타임 스템프에 의해 순차적으로 관리

- 클래스의 구조
  - up()과 down()메소드를 가짐
  - up() 메소드는 생성, 수정 등의 변화
  - down()은 단순히 up()메소드의 동작을 취소

##### 실행하기

```shell
php artisan migrate
php artisan migrate --force  // 강제수행
```

##### 되돌리기 (Rollback)

```shell
php artisan migrate:rollback
php artisan migrate:rollback --step=5 // 5단계 뒤로
php artisan migrate:reset // 처음 단계로 돌아가기

php artisan migrate:refresh // 처음상태로 갔다가 돌아오기 (reset+migrate)
php artisan migrate:refresh --seed // 데이터베이스를 초기화 시키고 돌아오기
php artisan migrate:refresh --step=5 // 5단계만 취소했다 다시 수행
```

#### 테이블 관리

##### 생성

```php
Schema::create('users', function (Blueprint $table) {
    $table->increments('id');
});
```

##### 확인

```php
if (Schema::hasTable('users')) { ... } // 테이블
if (Schema::hasColumn('users', 'email')) { ... } // 컬럼
```

##### 커넥션 , 엔진

```php
Schema::connection('foo')->create('users', function (Blueprint $table) {
    $table->increments('id');
})
Schema::create('users', function (Blueprint $table) {
    $table->engine = 'InnoDB';
    $table->increments('id');
});
```

##### 이름 변경

```php
Schema::rename($from, $to); // 외래키 주의 (제약조건)
```

##### 삭제

```php
Schema::drop('users');
Schema::dropIfExists('users');
```

#### 컬럼

```php
Schema::table('users', function (Blueprint $table) {
    $table->string('email');
});
```

```php

```

```php
```
