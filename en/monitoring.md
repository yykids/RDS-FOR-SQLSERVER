## Database > RDS for SQL Server > Monitoring

Performance indicators of a database instance, as well as events occurred at a database instance, backup, parameter group or security group can be monitored. DB 인스턴스의 각종 성능 지표 및 DB 인스턴스, 백업, 파라미터 그룹과 보안 그룹에서 발생한 각종 이벤트를 모니터링할 수 있습니다.

## 서버 대시보드 Server Dashboard

Server Dashboard helps to visualize performance indicators on a chart. Indicators are collected at every minute and retained for up to 5 years. Indicator data are collected by the average of 5 minutes, 30 minutes, 2 hours, or 1 day. Each collecting unit provides different retention period like below:  서버 대시보드를 통해 성능 지표를 차트 형태로 시각화 하여 볼수 있습니다. 지표는 1분에 한번씩 수집되며 최대 5년간 보관됩니다. 지표 데이터는 5분, 30분, 2시간, 1일 단위의 평균값으로 집계됩니다. 집계 단위별 보관 기간은 아래와 같습니다.

| Unit of Collecting 집계 단위 | Retention Period보관 기간 |
| - | - |
| 1 minute | 7 days |
| 5 minutes | 1 month |
| 30 minutes | 6 months |
| 2 hours | 2 years |
| 1 day | 5 years |

Chart layout is made available as user needs, and many number of layouts can be created to meet management purposes.  차트는 원하는 레이아웃으로 배치할 수 있으며, 레이아웃을 여러 개 생성해 목적에 따라 관리할 수 있습니다.

## 이벤트 Event

이벤트는 RDS for SQL Server 혹은 사용자에 의해 발생한 중요 사건을 의미합니다. 이벤트는 이벤트의 유형과 발생 일시, 원본 소스와 메시지로 구성됩니다. 이벤트는 웹 콘솔에서 조회 가능하며, 구독을 통해 이메일, SMS, 웹훅을 통해 이벤트 발생 알림을 받을 수 있습니다. 이벤트의 유형과 발생 가능한 이벤트는 아래와 같습니다. An event refers to an important incident incurred by RDS for SQL Server or user. An event is comprised of a category, date of occurrence, original source and message. It can be queried on a web console and notified via email, SMS, or webshook on subscription. Each event category may include event occurrences, like follows:  

| Event Category 이벤트 유형 | Event Code이벤트 코드 | Event Message 이벤트 메시지 |
| - | - | - |
| DB_INSTANCE | DB_INSTANCE_CREATED | Database instance created DB 인스턴스 생성 |
| DB_INSTANCE | DB_INSTANCE_CREATED_FAIL | Creating DB instance failed DB 인스턴스 생성 실패 |
| DB_INSTANCE | DB_INSTANCE_BACKUP_START | DB Instance backup started DB 인스턴스 백업 시작 |
| DB_INSTANCE | DB_INSTANCE_BACKUP_END | DB instance backed up 인스턴스 백업 완료 |
| DB_INSTANCE | DB_INSTANCE_BACKUP_FAIL | Backup of DB instance failed 인스턴스 백업 실패 |
| DB_INSTANCE | DB_INSTANCE_DELETED | Backup of DB instance deleted 인스턴스 백업 삭제 |
| DB_INSTANCE | DB_INSTANCE_DELETED_FAIL | Deleting DB instance backup failed 인스턴스 백업 삭제 실패 |
| DB_INSTANCE | DB_INSTANCE_RESTORE_START | DB instance restoration started 인스턴스 복원 시작 |
| DB_INSTANCE | DB_INSTANCE_RESTORE_END | DB instance restored  인스턴스 복원 완료 |
| DB_INSTANCE | DB_INSTANCE_RESTORE_FAIL | DB instance restoration failed  인스턴스 복원 실패 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_START | DB instance modification started 인스턴스 수정 시작 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_END | DB instance modified 인스턴스 수정 완료 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_FAIL | DB instance modification failed 인스턴스 수정 실패 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_START | Change of DB instance security group started 인스턴스 보안 그룹 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_END | Change of DB instance security group completed 인스턴스 보안 그룹 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_FAIL | Change of DB instance security group failed  인스턴스 보안 그룹 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_REBOOT_START | Restart of DB instance started  인스턴스 재시작 시작 |
| DB_INSTANCE | DB_INSTANCE_REBOOT_END | Restart of DB instance completed  인스턴스 재시작 완료 |
| DB_INSTANCE | DB_INSTANCE_REBOOT_FAIL | Restart of DB instance failed 인스턴스 재시작 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_START | Change of DB instance password started  인스턴스 비밀번호 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_END | Change of DB instance password completed 인스턴스 비밀번호 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_FAIL | Change of DB instance password failed 인스턴스 비밀번호 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_START | DB 인스턴스 포트 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_END | DB 인스턴스 포트 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_FAIL | DB 인스턴스 포트 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_START | DB 인스턴스 파라미터 그룹 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_END | DB 인스턴스 파라미터 그룹 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_FAIL | DB 인스턴스 파라미터 그룹 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_START | DB 인스턴스 타입 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_END | DB 인스턴스 타입 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_FAIL | DB 인스턴스 타입 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_START | DB 인스턴스 스토리지 크기 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_END | DB 인스턴스 스토리지 크기 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_FAIL | DB 인스턴스 스토리지 크기 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_START | DB 인스턴스 플로팅 IP 사용 여부 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_END | DB 인스턴스 플로팅 IP 사용 여부 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_FAIL | DB 인스턴스 플로팅 IP 사용 여부 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_START | DB 인스턴스 백업 설정 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_END | DB 인스턴스 백업 설정 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_FAIL | DB 인스턴스 백업 설정 변경 실패 |
| BACKUP | BACKUP_START | Backup started 백업 시작 |
| BACKUP | BACKUP_END | Backup completed 백업 완료 |
| BACKUP | BACKUP_DELETED | Backup deleted 백업 삭제 |
| PARAMETER_GROUP | PARAMETER_GROUP_CREATED | Parameter group created 파라미터 그룹 생성 |
| PARAMETER_GROUP | PARAMETER_GROUP_MODIFIED | Parameter group modified 파라미터 그룹 수정 |
| PARAMETER_GROUP | PARAMETER_GROUP_DELETED | Parameter group deleted 파라미터 그룹 삭제 |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_CREATED | DB security group created 보안 그룹 생성 |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_MODIFIED | DB security group modified 보안 그룹 수정 |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_DELETED | DB security group deleted 보안 그룹 삭제 |

### 이벤트 구독 Subscription of Events

이벤트 유형, 코드 및 소스로 구분하여 이벤트를 구독할 수 있습니다. 이벤트 유형으로 구독 시, 이벤트 유형에 포함된 모든 이벤트 코드에 대해서 알림을 받습니다. 알림이 너무 광범위할 경우 이벤트 코드와 소스로 세분화하여 구독할 수 있습니다. You may subscribe to events by each category, code or source. When subscribed by event category, for example, you'll be notified on every event code included in the event category. If the range of notification is too broad, subscription may be divided by event code or source.  

프로젝트의 멤버만 알림을 받을 사용자로 선택할 수 있습니다. 기본적으로 이메일로 이벤트 알림이 발송되며, 실명인증을 통해 휴대폰 번호가 등록된 경우에만 SMS 로 추가 이벤트 알림이 발송됩니다. 메일과 SMS 이외에도 웹훅을 등록하면 사전에 정의된 양식으로 HTTP 요청을 보냅니다. 웹훅의 양식은 아래와 같습니다.Only project members can be selected as notified users. By default, event notification is sent by email, and if mobile phone number is registered from real-name verification, additional notification is sent via SMS. In addition to email and SMS, with webhook registration, HTTP request is sent on a pre-defined form.

#### Method, URL
```
POST {URL for user-registered webhook사용자가 등록한 웹훅 URL}
Content-Type: application/json;charset=UTF-8
```

#### Request Body
```json
{
    "name": "Event Subscription Name이벤트 구독 이름",
    "source": "Event Source이벤트 소스",
    "sourceId": "Event Source ID이벤트 소스 아이디",
    "category": "Event Category이벤트 유형",
    "code": "Event Code이벤트 코드"
}
```
