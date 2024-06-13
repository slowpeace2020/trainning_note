# Database Design Document 

## Community Asset Module

- **Community Table: community**

| Field Name                | Data Type      | Nullable | Description           |
| ------------------------- | -------------- | -------- | --------------------- |
| community_id              | bigint(20)     | NO       | Community ID          |
| community_name            | varchar(128)   | YES      | Community Name        |
| community_code            | varchar(128)   | YES      | Community Code        |
| community_province_code   | varchar(32)    | YES      | Province Code         |
| community_city_code       | varchar(32)    | YES      | City Code             |
| community_town_code       | varchar(32)    | YES      | Town Code             |
| community_detailed_address| varchar(128)   | YES      | Detailed Address      |
| community_longitude       | varchar(32)    | YES      | Longitude             |
| community_latitude        | varchar(32)    | YES      | Latitude              |
| dept_id                   | bigint(32)     | YES      | Property ID           |
| community_sort            | int(11)        | YES      | Sort Order            |
| create_by                 | varchar(32)    | YES      | Creator               |
| create_time               | datetime       | YES      | Creation Time         |
| update_by                 | varchar(32)    | YES      | Updater               |
| update_time               | datetime       | YES      | Update Time           |
| remark                    | varchar(1024)  | YES      | Remark                |
|                           |                |          |                       |

- **Building Table: building**

| Field Name         | Data Type       | Nullable | Description   |
| ------------------ | --------------- | -------- | ------------- |
| building_id        | bigint(20)      | YES      | Building ID   |
| building_name      | varchar(32)     | YES      | Building Name |
| building_code      | varchar(32)     | YES      | Building Code |
| building_acreage   | decimal(32,10)  | YES      | Building Area |
| community_id       | bigint(20)      | YES      | Community ID  |
| create_by          | varchar(32)     | YES      | Creator       |
| create_time        | datetime        | YES      | Creation Time |
| update_by          | varchar(32)     | YES      | Updater       |
| update_time        | datetime        | YES      | Update Time   |
| remark             | varchar(1024)   | YES      | Remark        |
|                    |                 |          |               |

- **Unit Table: unit**

| Field Name           | Data Type       | Nullable | Description      |
| -------------------- | --------------- | -------- | ---------------- |
| unit_id              | bigint(20)      | YES      | Unit ID          |
| community_id         | bigint(20)      | YES      | Community ID     |
| building_id          | bigint(20)      | YES      | Building ID      |
| unit_name            | varchar(32)     | YES      | Unit Name        |
| unit_code            | varchar(128)    | YES      | Unit Code        |
| unit_level           | int(11)         | YES      | Number of Floors |
| unit_acreage         | decimal(32,10)  | YES      | Building Area    |
| unit_have_elevator   | varchar(32)     | YES      | Has Elevator     |
| create_by            | varchar(32)     | YES      | Creator          |
| create_time          | datetime        | YES      | Creation Time    |
| update_by            | varchar(32)     | YES      | Updater          |
| update_time          | datetime        | YES      | Update Time      |
| remark               | varchar(1024)   | YES      | Remark           |
|                      |                 |          |                  |

- **Room Table: room**

| Field Name                | Data Type       | Nullable | Description           |
| ------------------------- | --------------- | -------- | --------------------- |
| room_id                   | bigint(20)      | YES      | Room ID               |
| community_id              | bigint(20)      | YES      | Community ID          |
| building_id               | bigint(20)      | YES      | Building ID           |
| unit_id                   | bigint(20)      | YES      | Unit ID               |
| room_level                | int(11)         | YES      | Floor Number          |
| room_code                 | varchar(32)     | YES      | Room Code             |
| room_name                 | varchar(32)     | YES      | Room Name             |
| room_acreage              | decimal(32,10)  | YES      | Building Area         |
| room_cost                 | decimal(32,10)  | YES      | Cost Factor           |
| room_status               | varchar(32)     | YES      | Room Status           |
| room_is_shop              | varchar(32)     | YES      | Is Shop               |
| room_is_commercial_house  | varchar(32)     | YES      | Is Commercial House   |
| room_house_type           | varchar(32)     | YES      | House Type            |
| create_by                 | varchar(32)     | YES      | Creator               |
| create_time               | datetime        | YES      | Creation Time         |
| update_by                 | varchar(32)     | YES      | Updater               |
| update_time               | datetime        | YES      | Update Time           |
| remark                    | varchar(1024)   | YES      | Remark                |
|                           |                 |          |                       |

- **Community Interaction Table: community_interaction**

| Field Name       | Data Type      | Nullable | Description           |
| ---------------- | -------------- | -------- | --------------------- |
| interaction_id   | bigint(20)     | NO       | Interaction ID        |
| community_id     | bigint(20)     | YES      | Community ID          |
| create_by        | varchar(32)    | YES      | Creator ID            |
| update_by        | varchar(32)    | YES      | Updater ID            |
| create_time      | datetime       | YES      | Creation Time         |
| update_time      | datetime       | YES      | Update Time           |
| content          | varchar(1024)  | YES      | Content               |
| del_flag         | int(2)         | YES      | Deletion Status (0 default, 1 deleted) |
| remark           | varchar(255)   | YES      | Remark                |
| user_id          | bigint(20)     | YES      | User ID               |
|                  |                |          |                       |

## Community Management Module

- **Owner Table: zy_owner**

| Field Name           | Data Type      | Nullable | Description                     |
| -------------------- | -------------- | -------- | ------------------------------- |
| owner_id             | bigint(20)     | NO       | Owner ID                        |
| owner_nickname       | varchar(30)    | YES      | Nickname                        |
| owner_real_name      | varchar(30)    | YES      | Real Name                       |
| owner_gender         | varchar(10)    | YES      | Gender (unknown/male/female)    |
| owner_age            | int(3)         | YES      | Age                             |
| owner_id_card        | varchar(20)    | YES      | ID Card Number                  |
| owner_phone_number   | varchar(11)    | YES      | Phone Number                    |
| owner_open_id        | varchar(64)    | YES      | OpenID                          |
| owner_wechat_id      | varchar(64)    | YES      | WeChat ID                       |
| owner_qq_number      | varchar(20)    | YES      | QQ Number                       |
| owner_birthday       | date           | YES      | Birthday                        |
| owner_portrait       | varchar(256)   | YES      | Portrait                        |
| owner_signature      | varchar(64)    | YES      | Signature                       |
| owner_status         | varchar(10)    | YES      | Status (enable/disable)         |
| owner_logon_mode     | varchar(10)    | YES      | Registration Mode (WeChat/app/web) |
| owner_type           | varchar(32)    | YES      | Owner Type                      |
| owner_password       | varchar(128)   | YES      | Password                        |
| create_by            | varchar(32)    | YES      | Creator                         |
| create_time          | datetime       | YES      | Creation Time                   |
| update_by            | varchar(32)    | YES      | Updater                         |
| update_time          | datetime       | YES      | Update Time                     |
| remark               | varchar(1024)  | YES      | Remark                          |

- **House Binding Table**

| Field Name      | Data Type      | Nullable | Description                        |
| --------------- | -------------- | -------- | ---------------------------------- |
| owner_room_id   | bigint(20)     | NO       | House Binding ID                   |
| community_id    | bigint(20)     | YES      | Community ID                       |
| building_id     | bigint(20)     | YES      | Building ID                        |
| unit_id         | bigint(20)     | YES      | Unit ID                            |
| room_id         | bigint(20)     | YES      | Room ID                            |
| owner_id        | bigint(20)     | YES      | Owner ID                           |
| owner_type      | varchar(32)    | YES      |