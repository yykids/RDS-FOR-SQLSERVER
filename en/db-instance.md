## Database > RDS for SQL Server > Database Instance

Database instance 인스턴스는 가상 장비와 설치된 Microsoft SQL Server 를 아우르는 개념으로, RDS for SQL Server 에서 제공하는 Microsoft SQL Server 의 단위입니다. Database instance encompasses virtual equipment and installed Microsoft SQL Server, serving as the unit of Microsoft SQL Server provided by RDS for SQL Server. 
Direct access to a database instance is not allowed, but access is enabled only through the port entered when creating the database instance. DB 인스턴스의 운영체제에 직접 접근할 수 없으며, 오직 DB 인스턴스 생성 시 입력하신 포트를 통해서 데이터베이스로만 접근 할 수 있습니다.
DB 인스턴스는 고객이 부여하는 이름과 자동으로 부여되는 32바이트 아이디로 식별됩니다. 
DB 인스턴스 이름은 아래와 같은 제약사항이 있습니다. A database instance must be named, considering the following constraints: 

* DB 인스턴스 이름은 리전별로 고유해야 합니다. Must be unique for each region. 
* DB 인스턴스 이름은 4 ~ 100 사이의 알파벳, 숫자, - _ . 만 사용 가능합니다. Must be comprised of alphabets, numbers, -, _ ,and .only, between 4 and 100 characters.
* DB 인스턴스 이름의 첫 번째 문자는 글자이어야 합니다. Must start with a letter 

DB 인스턴스는 생성 시, 사용자 계정과 비밀번호를 설정해야 하며, 아래와 같은 제약사항이 있습니다. To create a database instance, user account and password setting is required, considering the following constraints: 

* 사용자 계정은 4 ~ 16자 사이의 알파벳, 숫자만 입력 가능하며, 첫 번째 문자는 글자이어야 합니다. A user account must be between 4 and 16 characters, comprised of alphabets and numbers only, starting with a letter. 
* 비밀번호는 8 ~ 128자 사이의 알파벳, 숫자, !, $, #, % 만 사용 가능합니다. A password must be between 8 and 128, comprised of alphabets, numbers, !, $, #, and % only. 
* 비밀번호에는 사용자의 계정 이름이 포함될 수 없습니다. Password cannot include user's account name. 
* 비밀번호는 대문자, 소문자, 숫자, 특수문자 중 세 범주의 문자를 포함해야 합니다. Password must include at least three categories out of capital letters, small-case letters, numbers, and special characters. 

### 가용성 영역 Availability Area

RDS for SQL Server 는 물리 하드웨어 문제로 생기는 장애에 대비하기 위해 전체 시스템을 여러 개의 가용성 영역으로 나누어 두었습니다. 한 가용성 영역 내에서 생기는 장애는 다른 가용성 영역에 영향을 주지 않으므로 서비스 전체의 가용성이 높아집니다. 서로 다른 가용성 영역에 흩어져서 생성된 DB 인스턴스끼리 네트워크 통신이 가능하며 이때 발생하는 네트워크 사용 비용은 부과되지 않습니다.

> [Caution]
> 이미 생성한 DB 인스턴스의 가용성 영역은 변경할 수 없습니다. It is unavailable to change the availability area of a created database instance. 

### Microsoft SQL Server 버전

SQL Server 2016 Standard 버전만 지원합니다.

### DB 인스턴스 타입 Database Instance Type

DB 인스턴스는 타입에 따라 서로 다른 CPU 코어 수와 메모리 용량을 가지고 있습니다.
DB 인스턴스 생성 시, 데이터베이스 워크로드에 따라 알맞은 DB 인스턴스 타입을 선택해야 합니다.

| 타입 Type    | 설명 Description |
| ------- | -------------------------------------------------|
| m2 | CPU와 메모리를 균형 있게 설정한 타입입니다. |
| c2 | CPU의 성능을 높게 설정한 인스턴스 타입입니다. |
| r2 | 다른 자원에 비해 메모리의 사용량이 많은 경우 사용할 수 있습니다. |

이미 생성한 DB 인스턴스의 타입은 웹 콘솔을 통해 손쉽게 변경 가능합니다.

> [Caution 주의]
> 이미 생성한 DB 인스턴스의 타입 변경 시, DB 인스턴스가 종료되므로 수분의 다운 타임이 발생합니다.

### 스토리지 타입 Storage Type

DB 인스턴스는 HDD, SSD 2가지 스토리지 타입을 지원합니다.Database instances support two storage types: HDD or SSD. 
스토리지 타입에 따라 성능과 가격이 다르므로, 데이터베이스 워크로드에 따라 알맞은 스토리지 타입을 선택해야 합니다.
스토리지 타입은 최소 20GB ~ 2,000GB 까지 생성 할 수 있습니다.
이미 생성한 스토리지의 크기는 웹 콘솔을 통해 손쉽게 변경 가능합니다.

> [Caution]
> 이미 생성한 스토리지의 크기 변경 시, DB 인스턴스가 종료되므로 수분의 다운 타임이 발생합니다.
> 이미 생성한 스토리지의 타입은 변경할 수 없습니다.
