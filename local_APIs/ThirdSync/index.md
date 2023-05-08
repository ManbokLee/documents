# Third Party Service Case Sync
> Currently, this API is only supported in RAYTeams version 1.0.33.2

## Case Sync API
### API
- URL: http://localhost:8008/api/file/raylinkthirdup
- Method: POST
- Params
  - Body Params
  - type: JSON
    ```JSON
    {
      "source": "C://Users//manbok.lee.RAYMEDICAL//Documents//test_data//rayface//",
      "projecttype": "DENTALAVATAR",
      "servicename": "trio-clear",
      "sitemid": "s008",
      "projectname": "string-0000",
      "pid": "string-0000"
    }
    ```
    | prop | type | required | description | 
    | -- | -- | -- | -- |
    | source | string | true | The root path of origin source   | 
    | projecttype | string | true | Project type of case | 
    | servicename | string | true | The name of the service that calls this API should be entered as "trio-clear" if the service name is "Trio-Clear". | 
    | sitemid | string | true | The ID managed by the calling source, which represents a unique value managed by the service calling the API. | 
    | projectname | string | false | default: sitemid <br> The name of the project that identifies the case. If this value is not present, the server will use "sitemid" instead.| 
    | pid | string| false | default: sitemid <br> The unique ID of the patient. If this value is not present, the server will use "sitemid" instead. |

- Responses
  - Success
    ```JSON
    {
      "status": "success",
      "data": {
        "source": "C://Users//manbok.lee.RAYMEDICAL//Documents//test_data//rayface//",
        "projecttype": "DENTALAVATAR",
        "servicename": "trio-clear",
        "sitemid": "s011",
        "pid": "s011",
        "projectname": "s011",
        "up": true,
        "ownerGroupId": "62dfdeb670a5ede021700e82",
        "labId": "62dfdeb670a5ede021700e82",
        "gId": "62dfdeb670a5ede021700e82",
        "distPath": "userdata/62dfdeb670a5ede021700e82/62dfdeb670a5ede021700e82/s011/s011",
        "attached": false
      }
    }
    ```
    | prop | description |
    | -- | -- |
    | status | success code |
    | data.source | The value entered during API call. |
    | data.projecttype | The value entered during API call. |
    | data.servicename | The value entered during API call. |
    | data.sitemid | The value entered during API call. |
    | pid | The value entered during API call or "sitemid" if no value was entered. |
    | projectname | The value entered during API call or "sitemid" if no value was entered. |
    | up | Synchronization flag, which always returns true. |
    | ownerGroupId | The group ID of the logged-in user. |
    | labId | The group ID of the logged-in user. |
    | gid | The group ID of the logged-in user. |
    | distPath | The path where the file will be uploaded to AWS S3. This value is the predicted result based on the assumption that the case will be successfully uploaded to S3. |
    | attached | False is returned when the case is initially shared, but if it is shared again, additional files will be uploaded to S3, and this value will be returned as true. |
  - Fail. Wrong servicename
    ```JSON
    {
      "status": "fail",
      "errmsg": "Not Allowed Third Service",
      "errors": [],
    }
    ```
    - Occurs when an unreserved value arrives in "servicename".
  - Fail. None Param
    ```JSON
    {
      "status": "fail",
      "errmsg": "Param Error",
      "errors": [],
    }
    ```
    - Occurs when any of the following values do not arrive: source, projecttype, servicename, or sitemid.
  - Fail. None User
    ```JSON
    {
      "status": "fail",
      "errmsg": "Not Find User",
      "errors": [],
    }
    ```
    - Occurs when there is no logged-in user in RAYTeams. This value is the first user authentication filter function for case sharing, and does not identify when login authentication is invalidated due to token expiration in the actual RAYTeams Client.
  - Fail. None Group
    ```JSON
    {
      "status": "fail",
      "errmsg": "Not find Group ID",
      "errors": [],
    }
    ```
    - Occurs when the Group ID does not exist for a user in RAYTeams. This only occurs when there is incorrect user data.

    