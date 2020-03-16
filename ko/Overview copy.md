## Database > RDS for SQL Server > 개요

TOAST Cloud Relational Database Service for SQL Server (RDS for SQL Server) 는 Microsoft SQL Server 를 클라우드 환경에서 제공하는 서비스입니다.
복잡한 설정 없이 고가용성의 Microsoft SQL Server 를 사용할 수 있습니다.

## 특징 및 기능 

* RDS for SQL Server 는 사용자의 Compute & Network 서비스를 활성화해야만 사용할 수 있습니다.

### DB 인스턴스

* RDS for SQL Server 에서 제공하는 Microsoft SQL Server 의 단위입니다.
* DB 인스턴스는 가상 장비와 설치된 Microsoft SQL Server 를 아우르는 개념입니다.
* DB 인스턴스는 최소 20GB~1,000GB 크기의 HDD 및 SSD 스토리지를 지원합니다.
* DB 인스턴스의 운영체제에 직접 접근 할 수 없으며, 오직 DB 인스턴스 생성 시 입력하신 port 를 통해서 Database 로만 접근 할 수 있습니다.
* DB 인스턴스 생성시 사용자의 Compute & Network 서비스의 VPC 서브넷을 선택해야만 생성할 수 있습니다.
* 연결된 VPC 서브넷에 있는 DB 인스턴스와 Compute & Network 서비스의 인스턴스 간에는 네트워크 연결이 활성화 됩니다.
* DB 인스턴스는 사용자의 VPC 서브넷 이외의 외부 네트워크와 단절되어 있습니다. 외부에서 연결을 원하면 플로팅 IP 를 붙여야 합니다.

### 백업

* Database 의 데이터를 복구할 수 있도록 미리 준비할 수 있습니다.
* 원하는 시점에 수동으로 백업을 생성하거나 일정 기간동안 자동으로 백업을 생성할 수 있습니다.
* 백업 파일은 별도의 오브젝트 스토리지에 저장되며 별도의 과금이 부과됩니다.
* 수동 백업은 사용자가 명시적으로 삭제하지 않는 한 지워지지 않습니다.
* 자동 백업은 사용자가 명시한 기간에 따라 최대 30일까지 저장됩니다.
* DB 인스턴스가 삭제되면 자동 백업도 같이 삭제 됩니다.
* 백업이 실행되는 동안에는 백업으로 인한 성능 저하가 발생 할 수 있습니다.
* 서비스에 영향을 주지 않기 위해서, 서비스의 부하가 적은 시간에 백업을 하는 것이 유리합니다.
* 

### 이벤트

* 