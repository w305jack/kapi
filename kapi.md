FORMAT: 1A
HOST: https://kapi-test.herokuapp.com/api/v1

# kapi

Kapi是內部開發所使用的.

## 咖啡店 [/cafes{?limited_time}{?socket}{?standing_desk}{?mrt}{?city}]

### 查詢 [GET]

查詢咖啡店資料

+ Parameters

    + limited_time (optional,number)

        限制時間

    + socket (optional,number)

        插座

    + standing_desk (optional,number)

        站立位

    + mrt (optional,string)

        捷運站

    + city (optional,string)

        城市

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

+ Response 200 (application/json)

        [
            {
                "id": "00014645-38c8-4eb4-ad9b-faa871d7e511",
                "address": "\u5609\u7fa9\u5e02\u6771\u5340\u5fe0\u5b5d\u8def205\u865f",
                "name": "R5\u5c0f\u9910\u9928",
                "phone": "052770250",
                "city": "chiayi",
                "latitude": 23.4838654,
                "longitude": 120.4535834,
                "standing_desk": 2
                "socket": 3,
                "limited_time": 3,
                "url": null,
                "fb_url": "https://www.facebook.com/r5.bistro",
                "mrt": null,
                "business_hour": {
                    "sun_1_open": "11:30",
                    "wed_1_open": "11:30",
                    "sat_1_open": "11:30",
                    "sun_1_close": "21:00",
                    "thu_1_open": "11:30",
                    "mon_1_open": "11:30",
                    "wed_1_close": "21:00",
                    "sat_1_close": "21:00",
                    "tue_1_open": "11:30",
                    "thu_1_close": "21:00",
                    "fri_1_close": "21:00",
                    "mon_1_close": "21:00",
                    "fri_1_open": "11:30",
                    "tue_1_close": "21:00"
                },
                "tags": null,
                "rates": {
                    "seat": 5.0,
                    "food": null,
                    "average": 5.0,
                    "wifi": 5.0,
                    "quiet": 5.0,
                    "tasty": 5.0,
                    "music": 5.0,
                    "cheap": 5.0
                },
                "photos": {
                    "google_s": "https://maps.googleapis.com/maps/api/place/photo?xxxx",
                    "google_l": "https://maps.googleapis.com/maps/api/place/photo?xxxx"
                },
                "is_kapi": false,
            },
            …
        ]

### 新增 [POST]

新增咖啡店資料

+ name:  有間咖啡店 (string, required) - 咖啡店名子
+ address: 忠孝東路 (string, required) - 咖啡店地址
+ city: taipei (string, required) - 所在城市
+ latitude: 23.4828654 (number, required) - 緯度
+ longitude: 120.4535834 (number, required) - 經度
+ id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string) - uuid，不填時自動產生
+ url: www.xxx.com (string) - 官方網站網址
+ fb_url: www.facebook.com/123456 (string) - Facebook網址
+ limited_time: 4 (string) - 限制時間 (1:很多,2:很少,3:看狀況,4:沒設定)
+ socket: 4 (string) - 插座 (1:很多,2:很少,3:看狀況,4:沒設定)
+ standing_desk: 4 (string) - 站立位 (1:很多,2:很少,3:看狀況,4:沒設定)
+ mrt: 忠孝敦化 (string) - 捷運站
+ phone: 23456789 (string) - 電話號碼
+ created_date: 1415203908 (string) - Timestamp，建立日期，不含小數點部分

+ Request 

    + Headers

            Content-Type: multipart/form-data
            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo



    + Body

            {
                "id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                "name":"有間咖啡廳",
                "address":"忠孝東路",
                "city":"taipei",
                "latitude":23.4838654,
                "longitude":120.4535834,
                "url":"",
                "fb_url": "",
                "limited_time": "4",
                "socket": "4",
                "standing_desk": "2",
                "mrt": "忠孝敦化",
                "phone": "0212345678",
                "created_date": "1492489712"
            }

+ Response 201 (application/json)

        {
            "result": true,
            "data": {
                "id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                "name": "\u6709\u9593\u5496\u5561\u5ef3",
                "address": "\u5fe0\u5b5d\u6771\u8def",
                "latitude": 23.4838654,
                "longitude": 120.4535834,
                "url": "",
                "fb_url": "",
                "limited_time": 4,
                "socket": 4,
                "standing_desk": 2,
                "mrt": "",
                "city": "taipei",
                "phone": "",
                "created_date": 1492489712,
                "is_kapi": true
            }
        }

### 更新 [PUT]

更新咖啡店資料

+ id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string, required) - id
+ name:  有間咖啡店 (string) - 咖啡店名子
+ address: 忠孝東路 (string) - 咖啡店地址
+ city: taipei (string) - 所在城市
+ latitude: 23.4828654 (number) - 緯度
+ longitude: 120.4535834 (number) - 經度
+ url: www.xxx.com (string) - 官方網站網址
+ fb_url: www.facebook.com/123456 (string) - Facebook網址
+ limited_time: 4 (string) - 限制時間 (1:很多,2:很少,3:看狀況,4:沒設定)
+ socket: 4 (string) - 插座 (1:很多,2:很少,3:看狀況,4:沒設定)
+ standing_desk: 4 (string) - 站立位 (1:很多,2:很少,3:看狀況,4:沒設定)
+ mrt: 忠孝敦化 (string) - 捷運站
+ phone: 23456789 (string) - 電話號碼
+ created_date: 1415203908 (string) - Timestamp，建立日期，不含小數點

+ Request
    
    + Headers

            Content-Type: multipart/form-data
            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                "name":"有間咖啡廳",
                "address":"忠孝東路",
                "city":"taipei",
                "latitude":23.4838654,
                "longitude":120.4535834,
                "url":"",
                "fb_url": "",
                "limited_time": "4",
                "socket": "4",
                "standing_desk": "2",
                "mrt": "忠孝敦化",
                "phone": "0212345678"
            }

+ Response 204

        {
            "result": true,
            "data": {
                "id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                "name": "\u6709\u9593\u5496\u5561\u5ef3",
                "address": "\u5fe0\u5b5d\u6771\u8def",
                "latitude": 23.4838654,
                "longitude": 120.4535834,
                "url": "",
                "fb_url": "",
                "limited_time": 4,
                "socket": 4,
                "standing_desk": 2,
                "mrt": "",
                "city": "taipei",
                "phone": "",
                "created_date": 1492489712,
                "is_kapi": true
            }
        }


## 會員 [/members{?id}{?level}]

### 查詢 [GET]

查詢會員資料

+ Parameters

    + id (optional,string)

        id為firebase產生之unique id

    + level (optional,string)

        等級

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

+ Response 200 (application/json)

        [
            {
                "id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "display_name": "\u4e01\u67cf\u582f",
                "photo_url": "https://scontent.xx.fbcdn.net/v/t1.0-1/p100x100/xxxxxx.jpg",
                "default_location": "taipei",
                "intro": "is alan",
                "level": null,
                "exp": null,
                "email": "xxx@hotmail.com",
                "created_date": 1492491511,
                "favorites": [
                    "4a24c511-d78f-4814-84c0-1ff0e4feb890"
                ],
                "visits": [
                    "4a24c511-d78f-4814-84c0-1ff0e4feb890"
                ]
            }
        ]

### 修改 [PUT]

修改會員資料

+ id: M8okOL1VC5bHjjqVqYw4P3db1AK2 (string, required) — id為firebase產生的unique id
+ display_name: 無名氏 (string) — 顯示名稱
+ photo_url: https://scontent.xx.fbcdn.net/v/t1.0-1/p100x100/xxxxxx.jpg (string) — 圖片url
+ email: xxx@hotmail.com (string) — 信箱
+ default_location: taipei (string) — 預設地區
+ intro: 我是kapi的忠實... — 介紹
+ level: 5 (string) — 等級
+ exp: 10 (string) — 經驗

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "display_name": "無名氏",
                "photo_url": "https://scontent.xx.fbcdn.net/v/t1.0-1/p100x100/xxxxxx.jpg",
                "default_location": "taipei",
                "intro": "我是kapi的忠實...",
                "level": 5,
                "exp": 10,
                "email": "xxx@hotmail.com"
            }

+ Response

        {
            "result": true,
            "data": {
                "display_name": "\u4e01\u67cf\u582f",
                "photo_url": "https://scontent.xx.fbcdn.net/v/t1.0-1/p100x100/xxxxxx.jpg",
                "default_location": "taipei",
                "intro": "...",
                "level": 5,
                "exp": 10,
            }
        }


## 最愛 [/favorites{?member_id}{?cafe_id}]

### 查詢 [GET]

查詢會員資料

+ Parameters

    至少選擇一個參數做查詢

    + member_id (string)

        id為firebase產生之unique id

    + cafe_id (string)

        咖啡店id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

+ Response 200 (application/json)

        [
            {
                "id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "favorites": [
                    "4a24c511-d78f-4814-84c0-1ff0e4feb890"
                ]
            }
        ]

### 新增 [POST]

新增最愛資料

+ member_id: M8okOL1VC5bHjjqVqYw4P3db1AK2 (string, required) — 會員id為firebase產生的unique id
+ cafe_id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string, required) — 咖啡店id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890"
            }

+ Response

        {
            "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
            "favorites": [
                "4a24c511-d78f-4814-84c0-1ff0e4feb890"
            ]
        }

### 刪除 [Delete]

刪除最愛資料

+ member_id: M8okOL1VC5bHjjqVqYw4P3db1AK2 (string, required) — 會員id為firebase產生的unique id
+ cafe_id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string, required) — 咖啡店id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890"
            }

+ Response

        {
            "result": true
        }


## 到訪 [/visits{?member_id}{?cafe_id}]

### 查詢 [GET]

查詢到訪資料

+ Parameters

    選擇一個做參數查詢即可

    + member_id (string)

        id為firebase產生之unique id

    + cafe_id (string)

        咖啡店id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

+ Response 200 (application/json)

        [
            {
                "id": "M8okOL1VC5bHjjqVqYw4P3db1AK2"
                "visits": [
                    "4a24c511-d78f-4814-84c0-1ff0e4feb890"
                ]
            }
        ]

### 新增 [POST]

新增到訪資料

+ member_id: M8okOL1VC5bHjjqVqYw4P3db1AK2 (string, required) — 會員id為firebase產生的unique id
+ cafe_id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string, required) — 咖啡店id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890"
            }

+ Response

        {
            "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
            "visits": [
                "4a24c511-d78f-4814-84c0-1ff0e4feb890"
            ]
        }

### 刪除 [Delete]

刪除到訪資料

+ member_id: M8okOL1VC5bHjjqVqYw4P3db1AK2 (string, required) — 會員id為firebase產生的unique id
+ cafe_id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string, required) — 咖啡店id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890"
            }

+ Response

        {
            "result": true
        }


## 標籤 [/tags{?cafe_id}{?tag_id}]

### 查詢 [GET]

查詢標籤資料

+ Parameters

    + cafe_id (string)

        咖啡店id

    + tag_id (string)

        標籤id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

+ Response 200 (application/json)

        無參數時

        [
            {
                "tag_name": "\u5fa9\u53e4",
                "id": "76f21fa3-88ad-4d69-976c-53d769af978f"
            },
            {
                "tag_name": "\u6416\u6efe",
                "id": "dae7755c-376c-451f-ae68-b0d39ab0e33e"
            }
        ]

        參數有cafe_id時

        [
            {
                "id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                "name": "\u6709\u9593\u5496\u5561\u5ef3",
                "address": "\u5fe0\u5b5d\u6771\u8def123\u865f",
                "latitude": 21.212122,
                "longitude": 121.21212,
                "url": "",
                "fb_url": "",
                "limited_time": 4,
                "socket": 4,
                "standing_desk": 2,
                "mrt": "",
                "city": "taipei",
                "phone": "",
                "created_date": 1492489712,
                "is_kapi": true,
                "tags": [
                    {
                        "id": "76f21fa3-88ad-4d69-976c-53d769af978f",
                        "tag_name": "\u5fa9\u53e4"
                    },
                    {
                        "id": "dae7755c-376c-451f-ae68-b0d39ab0e33e",
                        "tag_name": "\u6416\u6efe"
                    }
                ],
                "business_hour": null,
                "rate": null,
                "photos": null
            },
            ...
        ]


### 新增 [POST]

新增標籤資料

+ tag_name: 復古風 (string, required)

新增咖啡店的標籤

+ cafe_id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string, required) — 咖啡店id
+ tag_id: 76f21fa3-88ad-4d69-976c-53d769af978f (string, required) - 標籤id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            新增標籤

            {
                "tag_name": "復古風"
            }

            新增咖啡店的標籤

            {
                "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                "tag_id": "76f21fa3-88ad-4d69-976c-53d769af978f"
            }

+ Response

        新增標籤

        {
            "result": true,
            "data": {
                "tag_name": "\u5fa9\u53e4",
                "id": "76f21fa3-88ad-4d69-976c-53d769af978f"
            }
        }

        新增咖啡店的標籤

        {
            "result": true
        }


## 營業時間 [/hours{?cafe_id}]

### 查詢 [GET]

查詢營業時間資料

+ Parameters

    + cafe_id (required,string)

        咖啡店id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

+ Response 200 (application/json)

        {
            "cafe_id": "00014645-38c8-4eb4-ad9b-faa871d7e511",
            "hours": {
                "sun_1_open": "11:30",
                "wed_1_open": "11:30",
                "sat_1_open": "11:30",
                "sun_1_close": "21:00",
                "thu_1_open": "11:30",
                "mon_1_open": "11:30",
                "wed_1_close": "21:00",
                "sat_1_close": "21:00",
                "tue_1_open": "11:30",
                "thu_1_close": "21:00",
                "fri_1_close": "21:00",
                "mon_1_close": "21:00",
                "fri_1_open": "11:30",
                "tue_1_close": "21:00"
            }
        }

### 新增 [POST]

新增營業時間資料

+ cafe_id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string, required) - 咖啡店id
+ hours: {"sun_1_open":"11:30", ...} (dict, required) - 營業時間

+ Request 

    + Headers

            Content-Type: application/json
            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "id": "00014645-38c8-4eb4-ad9b-faa871d7e511",
                "hours": {
                    "sun_1_open": "11:30",
                    "wed_1_open": "11:30",
                    "sat_1_open": "11:30",
                    "sun_1_close": "21:00",
                    "thu_1_open": "11:30",
                    "mon_1_open": "11:30",
                    "wed_1_close": "21:00",
                    "sat_1_close": "21:00",
                    "tue_1_open": "11:30",
                    "thu_1_close": "21:00",
                    "fri_1_close": "21:00",
                    "mon_1_close": "21:00",
                    "fri_1_open": "11:30",
                    "tue_1_close": "21:00"
                }
            }

+ Response 201 (application/json)

            {
                "result": true,
                "data": {
                    "hours": {
                        "mon_1_open": null,
                        "mon_1_close": null,
                        "tue_1_open": "12:00",
                        "tue_1_close": "21:00",
                        "wed_1_open": "12:00",
                        "wed_1_close": "21:00",
                        "thu_1_open": "12:00",
                        "thu_1_close": "21:00",
                        "fri_1_open": "12:00",
                        "fri_1_close": "21:00",
                        "sat_1_open": "11:00",
                        "sat_1_close": "21:00",
                        "sun_1_open": "11:00",
                        "sun_1_close": "21:00"
                    }
                }
            }

### 更新 [PUT]

更新營業時間資料

+ cafe_id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string, required) - 咖啡店id
+ hours: {"sun_1_open":"11:30", ...} (dict, required) - 營業時間

+ Request
    
    + Headers

            Content-Type: application/json
            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "id": "00014645-38c8-4eb4-ad9b-faa871d7e511",
                "hours": {
                    "sun_1_open": "11:30",
                    "wed_1_open": "11:30",
                    "sat_1_open": "11:30",
                    "sun_1_close": "21:00",
                    "thu_1_open": "11:30",
                    "mon_1_open": "11:30",
                    "wed_1_close": "21:00",
                    "sat_1_close": "21:00",
                    "tue_1_open": "11:30",
                    "thu_1_close": "21:00",
                    "fri_1_close": "21:00",
                    "mon_1_close": "21:00",
                    "fri_1_open": "11:30",
                    "tue_1_close": "21:00"
                }
            }

+ Response 204

        {
            "result": true,
            "data": {
                "hours": {
                    "mon_1_open": null,
                    "mon_1_close": null,
                    "tue_1_open": "12:00",
                    "tue_1_close": "21:00",
                    "wed_1_open": "12:00",
                    "wed_1_close": "21:00",
                    "thu_1_open": "12:00",
                    "thu_1_close": "21:00",
                    "fri_1_open": "12:00",
                    "fri_1_close": "21:00",
                    "sat_1_open": "11:00",
                    "sat_1_close": "21:00",
                    "sun_1_open": "11:00",
                    "sun_1_close": "21:00"
                }
            }
        }


## 評分 [/rates{?cafe_id}]

### 查詢 [GET]

查詢評分資料

+ Parameters

    + id (optional, string)

        評分id

    + cafe_id (required, string)

        咖啡店id

    + member_id (required, string)

        會員id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

+ Response 200 (application/json)

        [
            {
                "result": true,
                "data": {
                    "id": "8ac378a5-c9d3-41f2-9054-0619fcca63f7",
                    "food": 5,
                    "wifi": 5,
                    "seat": null,
                    "quiet": 5,
                    "tasty": null,
                    "cheap": 5,
                    "music": null,
                    "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                    "member_id": "3607c037-765f-4686-a7ce-ded4ff0daa82"
                }
            },
            …
        ]

### 新增 [POST]

新增評分資料

+ cafe_id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string, required) - 咖啡店id
+ member_id: M8okOL1VC5bHjjqVqYw4P3db1AK2 (string, required) — 會員id為firebase產生的unique id
+ id: 8ac378a5-c9d3-41f2-9054-0619fcca63f7 (string, optional) - uuid，不填時自動產生

+ Request 

    + Headers

            Content-Type: application/json
            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                "member_id": "3607c037-765f-4686-a7ce-ded4ff0daa82",
                "id": "8ac378a5-c9d3-41f2-9054-0619fcca63f7",
                "food": 5,
                "wifi": 5,
                "seat": 4,
                "quiet": 5,
                "tasty": 3,
                "cheap": 5,
                "music": 2                
            }

+ Response 201 (application/json)

        {
            "result": true,
            "data": {
                "id": "8ac378a5-c9d3-41f2-9054-0619fcca63f7",
                "food": 5,
                "wifi": 5,
                "seat": 4,
                "quiet": 5,
                "tasty": 3,
                "cheap": 5,
                "music": 2,
                "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                "member_id": "3607c037-765f-4686-a7ce-ded4ff0daa82"
            }
        }

### 更新 [PUT]

更新評分資料

+ id: 8ac378a5-c9d3-41f2-9054-0619fcca63f7 (string, optional) - 評分id

+ Request
    
    + Headers

            Content-Type: application/json
            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "id": "8ac378a5-c9d3-41f2-9054-0619fcca63f7",
                "food": 3,
                "wifi": 3,
                "seat": 4,
                "quiet": 3,
                "tasty": 3,
                "cheap": 3,
                "music": 2                
            }

+ Response 204

        {
            "result": true,
            "data": {
                "id": "3acc548a-7520-4965-be5d-b6db0884c561",
                "food": 3,
                "wifi": 3,
                "seat": 4,
                "quiet": 3,
                "tasty": 3,
                "cheap": 3,
                "music": 2  
            }
        }


## 喜歡（按讚） [/likes]

### 更新 [PUT]

更新喜歡資料

+ member_id: M8okOL1VC5bHjjqVqYw4P3db1AK2 (string, required) - 會員id
+ comment_id: 4c86050e-616b-4adb-a16d-e3f85cd6c9a6 (string, required) - 留言id
+ like: true/false (boolean, required) - 是否喜歡
+ id: 99739b6c-2994-4fc4-88b8-a9788e0cfe5b (string) - uuid，不填時自動產生

+ Request
    
    + Headers

            Content-Type: application/json
            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "id": "99739b6c-2994-4fc4-88b8-a9788e0cfe5b"
                "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "comment_id": "4c86050e-616b-4adb-a16d-e3f85cd6c9a6",
                "like": true,
            }

+ Response 204

        {
            "result": true,
            "data": {
                "id": "99739b6c-2994-4fc4-88b8-a9788e0cfe5b"
                "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "comment_id": "4c86050e-616b-4adb-a16d-e3f85cd6c9a6",
                "like": true,
            }
        }


## 評論 [/rates{?id}{?cafe_id}]

### 查詢 [GET]

查詢評論資料

+ Parameters

    至少選擇一個參數做查詢

    + id (string)

        評論id

    + cafe_id (string)

        咖啡店id

+ Request 

    + Headers

            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

+ Response 200 (application/json)

        [
            "id": "d9ff09cd-5fa1-4326-8668-aeb7ecf5ea78",
            "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
            "comments": [
                {
                    "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                    "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                    "review_id": "d9ff09cd-5fa1-4326-8668-aeb7ecf5ea78",
                    "id": "4c86050e-616b-4adb-a16d-e3f85cd6c9a6",
                    "comment": null,
                    "date": 1492518436,
                    "likes": [
                    ]
                ]
            },
            …
        ]

## 留言 [/comments{?cafe_id}{?member_id}]

### 新增 [POST]

新增留言資料

+ cafe_id: 4a24c511-d78f-4814-84c0-1ff0e4feb890 (string, required) - 咖啡店id
+ member_id: M8okOL1VC5bHjjqVqYw4P3db1AK2 (string, required) — 會員id為firebase產生的unique id
+ id: 8ac378a5-c9d3-41f2-9054-0619fcca63f7 (string) - uuid，不填時自動產生
+ review_id: 8ac378a5-c9d3-41f2-9054-0619fcca63f7 (string) - uuid，不填時自動產生
+ comment: 這是留言內容 (string) - 留言內容
+ date: 1492518436 (string) Timestamp，建立日期，不含小數點部分，不填時自動產生

+ Request 

    + Headers

            Content-Type: application/json
            token: eyJhbGciOiJIUzI1NiIsImlhdCI6MTQ5MjA4OTY2MCwiZXhwIjoxNDk0NzY4MDYwfQ.eyJpZCI6IjJjZmI2MDY1LWM1NTEtNDVkYy1iYjA0LTBmOGUyNTJjN2ViOSJ9.tvt3G1qgooHD3LoetN6Zc2c3Z256YbbrnlibbEHQjlo

    + Body

            {
                "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "review_id": "d9ff09cd-5fa1-4326-8668-aeb7ecf5ea78",
                "id": "4c86050e-616b-4adb-a16d-e3f85cd6c9a6",
                "comment": "這是留言",
                "date": 1492518436               
            }

+ Response 201 (application/json)

        {
            "result": true,
            "data": {
                "cafe_id": "4a24c511-d78f-4814-84c0-1ff0e4feb890",
                "member_id": "M8okOL1VC5bHjjqVqYw4P3db1AK2",
                "review_id": "d9ff09cd-5fa1-4326-8668-aeb7ecf5ea78",
                "id": "4c86050e-616b-4adb-a16d-e3f85cd6c9a6",
                "comment": "這是留言",
                "date": 1492518436
            }
        }
