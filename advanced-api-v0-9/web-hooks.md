+++
draft = false
title = "Web Hooks"
date = 2014-07-29T09:31:36Z
[menu.advanced_sidebar_v0_9]
    weight = -240
+++

### List web hooks

|   **Property**    |   **Description**                 |
|   -----------     |   ---------------                 |
|   Resource URL    |   `/api/hooks`                    |
|   Method          |   GET                             |
|   Type            |   None                            |
|   Body            |   None                            |
|   Param           |   None                            |

#### Sample Request:

    GET /api/hooks HTTP/1.1
    Host: localhost:3000
    authorization:7a7b140f-2480-4d5a-4e78-24049e3ba7f8

#### Sample Response:
    
    {
        "hooks": [
            {
                "api_model": {},
                "id": "54be6c0beba6db07a6000002",
                "org_id": "54b53d3aeba6db5c35000002",
                "name": "Test Post",
                "method": "POST",
                "target_path": "http://httpbin.org/post",
                "template_path": "",
                "header_map": {
                    "x-tyk-test": "123456"
                },
                "event_timeout": 0
            }
        ],
        "pages": 0
    }


### Get single web hook

|   **Property**    |   **Description**                 |
|   -----------     |   ---------------                 |
|   Resource URL    |   `/api/hooks/{hook-id}`          |
|   Method          |   GET                             |
|   Type            |   None                            |
|   Body            |   None                            |
|   Param           |   None                            |

#### Sample Request:

    GET /api/hooks/54be6c0beba6db07a6000002 HTTP/1.1
    Host: localhost:3000
    authorization:7a7b140f-2480-4d5a-4e78-24049e3ba7f8

#### Sample Response:

    {
        "api_model": {},
        "id": "54be6c0beba6db07a6000002",
        "org_id": "54b53d3aeba6db5c35000002",
        "name": "Test Post",
        "method": "POST",
        "target_path": "http://httpbin.org/post",
        "template_path": "",
        "header_map": {
            "x-tyk-test": "123456"
        },
        "event_timeout": 0
    }
    
### Add hook

|   **Property**    |   **Description**                 |
|   -----------     |   ---------------                 |
|   Resource URL    |   `/api/hooks`                    |
|   Method          |   POST                            |
|   Type            |   None                            |
|   Body            |   Hook object                     |
|   Param           |   None                            |

#### Sample Request:

    POST /api/hooks HTTP/1.1
    Host: localhost:3000
    authorization:7a7b140f-2480-4d5a-4e78-24049e3ba7f8
    
    {
        "name": "New Post Test",
        "method": "POST",
        "target_path": "http://httpbin.org/post",
        "header_map": {
            "x-test": "y-answer"
        }
    }    

#### Sample Response:

    {
        "Status": "OK",
        "Message": "Webhook created",
        "Meta": ""
    }

### Update hook

|   **Property**    |   **Description**                 |
|   -----------     |   ---------------                 |
|   Resource URL    |   `/api/hooks/{hook-id}`          |
|   Method          |   PUT                             |
|   Type            |   None                            |
|   Body            |   Hook object                     |
|   Param           |   None                            |

#### Sample Request:

    PUT /api/hooks/54c2617aeba6db1edc000003 HTTP/1.1
    Host: localhost:3000
    authorization:7a7b140f-2480-4d5a-4e78-24049e3ba7f8
    
    {
        "api_model": {},
        "id": "54c2617aeba6db1edc000003",
        "org_id": "54b53d3aeba6db5c35000002",
        "name": "New Post Test",
        "method": "PUT",
        "target_path": "http://httpbin.org/post",
        "template_path": "",
        "header_map": {
            "x-test": "y-answer"
        },
        "event_timeout": 0
    } 

#### Sample Response:

    {
        "Status": "OK",
        "Message": "Webhook updated",
        "Meta": ""
    }


### Delete web hook

|   **Property**    |   **Description**                 |
|   -----------     |   ---------------                 |
|   Resource URL    |   `/api/users`                    |
|   Method          |   DELETE                          |
|   Type            |   None                            |
|   Body            |   None                            |
|   Param           |   None                            |

#### Sample Request:

    DELETE / HTTP/1.1
    Host: localhost:3000
    authorization:7a7b140f-2480-4d5a-4e78-24049e3ba7f8

#### Sample Response:

    {
        "Status": "OK",
        "Message": "Webhook deleted",
        "Meta": ""
    }


