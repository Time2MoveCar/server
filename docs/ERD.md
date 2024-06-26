# uncar

> Generated by [`prisma-markdown`](https://github.com/samchon/prisma-markdown)

- [default](#default)

## default

```mermaid
erDiagram
"user" {
  String id PK
  String account UK
  String password
  String nickname UK
  String phone UK
  String contry_code
  DateTime created_at
  DateTime updated_at
  DateTime deleted_at "nullable"
}
"user_snapshot" {
  String id PK
  String userId FK
  String account
  String password
  String nickname
  String phone
  String contry_code
  DateTime created_at
}
"user_last_snapshot" {
  String user_id PK
  String snapshot_id FK
  DateTime created_at
  DateTime updated_at
}
"user_profile_image" {
  String user_id PK
  String image_id FK
  DateTime created_at
  DateTime updated_at
}
"terms_agreements" {
  String id PK
  String user_id FK
  TERMS_TYPE type
  Boolean agree
  DateTime created_at
  DateTime updated_at
}
"oauth" {
  String id PK
  String user_id FK
  OAUT_PROVIDER provider
  String provider_id
  DateTime created_at
  DateTime updated_at
}
"certification" {
  String id PK
  String certification_code_id FK
  String user_id FK
  CERTIFICATION_TARGET_TYPE targetType
  CERTIFICATION_TYPE type
  DateTime created_at
  DateTime updated_at
}
"certification_code" {
  String id PK
  CERTIFICATION_TARGET_TYPE targetType
  CERTIFICATION_TYPE type
  CERTIFICATION_STATUS status
  String code
  String target
  DateTime created_at
  DateTime updated_at
  DateTime expired_at
}
"car" {
  String id PK
  String owner_id FK
  String type
  String number UK
  DateTime created_at
  DateTime updated_at
}
"car_image" {
  String id PK
  String car_id FK
  String image_id FK
  DateTime created_at
  DateTime updated_at
}
"car_snapshot" {
  String id PK
  String car_id FK
  String owner_id
  String type
  String number UK
  DateTime created_at
  DateTime updated_at
}
"driving" {
  String id PK
  String user_id FK
  String car_id FK
  DateTime created_at
  DateTime updated_at
}
"parking" {
  String id PK
  String car_id FK
  String drivingId FK
  String location
  Float latitude
  Float longitude
  PARKING_STATUS status
  DateTime start_date
  DateTime end_date
  DateTime created_at
  DateTime updated_at
}
"parking_snapshot" {
  String id PK
  String car_id FK
  String drivingId
  String location
  Float latitude
  Float longitude
  PARKING_STATUS status
  DateTime start_date
  DateTime end_date
  DateTime created_at
}
"notification" {
  String id PK
  String user_id FK
  NOTIFICATION_TYPE type
  String title
  String content
  DateTime read_at "nullable"
  DateTime created_at
  DateTime updated_at
}
"user_reputation" {
  String id PK
  String user_id FK
  String writer_id FK
  Int score
  DateTime created_at
  DateTime updated_at
}
"user_reputation_reason" {
  String id PK
  String user_reputation_id FK
  REPUTATION_TYPE type
  Int score
  DateTime created_at
}
"image" {
  String id PK
  String user_id
  IMAGE_TYPE type
  String url
  DateTime created_at
  DateTime deleted_at "nullable"
}
"user_snapshot" }o--|| "user" : user
"user_last_snapshot" |o--|| "user" : user
"user_last_snapshot" |o--|| "user_snapshot" : snapshot
"user_profile_image" |o--|| "user" : user
"user_profile_image" |o--|| "image" : image
"terms_agreements" }o--|| "user" : user
"oauth" }o--|| "user" : user
"certification" }o--|| "user" : user
"certification" |o--|| "certification_code" : certificationCode
"car" }o--|| "user" : owner
"car_image" }o--|| "car" : car
"car_image" }o--|| "image" : image
"car_snapshot" }o--|| "car" : car
"driving" }o--|| "user" : user
"driving" }o--|| "car" : car
"parking" }o--|| "car" : car
"parking" }o--|| "driving" : driving
"parking_snapshot" }o--|| "parking" : parking
"notification" }o--|| "user" : user
"user_reputation" }o--|| "user" : user
"user_reputation" }o--|| "user" : writer
"user_reputation_reason" }o--|| "user_reputation" : userReputation
```

### `user`

**Properties**

- `id`:
- `account`:
- `password`:
- `nickname`:
- `phone`:
- `contry_code`:
- `created_at`:
- `updated_at`:
- `deleted_at`:

### `user_snapshot`

**Properties**

- `id`:
- `userId`:
- `account`:
- `password`:
- `nickname`:
- `phone`:
- `contry_code`:
- `created_at`:

### `user_last_snapshot`

**Properties**

- `user_id`: 사용자 ID
- `snapshot_id`: 스냅샷 ID
- `created_at`:
- `updated_at`:

### `user_profile_image`

**Properties**

- `user_id`: 사용자 ID
- `image_id`: 이미지 ID
- `created_at`:
- `updated_at`:

### `terms_agreements`

**Properties**

- `id`: 약관동의 ID
- `user_id`: 사용자 ID
- `type`:
- `agree`:
- `created_at`:
- `updated_at`:

### `oauth`

**Properties**

- `id`:
- `user_id`:
- `provider`:
- `provider_id`:
- `created_at`:
- `updated_at`:

### `certification`

**Properties**

- `id`:
- `certification_code_id`:
- `user_id`:
- `targetType`:
- `type`:
- `created_at`:
- `updated_at`:

### `certification_code`

**Properties**

- `id`:
- `targetType`:
- `type`:
- `status`:
- `code`:
- `target`:
- `created_at`:
- `updated_at`:
- `expired_at`:

### `car`

**Properties**

- `id`:
- `owner_id`:
- `type`:
- `number`:
- `created_at`:
- `updated_at`:

### `car_image`

**Properties**

- `id`:
- `car_id`:
- `image_id`:
- `created_at`:
- `updated_at`:

### `car_snapshot`

**Properties**

- `id`:
- `car_id`:
- `owner_id`:
- `type`:
- `number`:
- `created_at`:
- `updated_at`:

### `driving`

**Properties**

- `id`:
- `user_id`:
- `car_id`:
- `created_at`:
- `updated_at`:

### `parking`

**Properties**

- `id`:
- `car_id`:
- `drivingId`:
- `location`: 주차 위치 (주소)
- `latitude`:
- `longitude`:
- `status`:
- `start_date`:
- `end_date`:
- `created_at`:
- `updated_at`:

### `parking_snapshot`

**Properties**

- `id`:
- `car_id`:
- `drivingId`:
- `location`:
- `latitude`:
- `longitude`:
- `status`:
- `start_date`:
- `end_date`:
- `created_at`:

### `notification`

**Properties**

- `id`:
- `user_id`:
- `type`:
- `title`:
- `content`:
- `read_at`:
- `created_at`:
- `updated_at`:

### `user_reputation`

**Properties**

- `id`:
- `user_id`:
- `writer_id`:
- `score`:
- `created_at`:
- `updated_at`:

### `user_reputation_reason`

**Properties**

- `id`:
- `user_reputation_id`:
- `type`:
- `score`:
- `created_at`:

### `image`

**Properties**

- `id`:
- `user_id`:
- `type`:
- `url`:
- `created_at`:
- `deleted_at`:
