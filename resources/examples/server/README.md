# Time Pod Command

**Note:** This project follows the [code null guidelines](https://github.com/code-null/organization/blob/main/guidelines.md) in version v2.0.0.0

Server for handling the data for the Time Pod time keeping program.

## Status

Stage: Deprecated

Status: Online

Latest Stable Version: 3.0.12.8

## Technical Details

| Segment | Technical ID | Public ID            | Official Name    | Type   | Server Type | Requires Accounts | Technology | Versioning                                   |
| ------- | ------------ | -------------------- | ---------------- | ------ | ----------- | ----------------- | ---------- | -------------------------------------------- |
| Server  | S0183        | codnMngTimePodServer | Time Pod Command | manage | GraphQL     | true              | NodeJS     | [CNV 1.0.0.0](../resources/cn_versioning.md) |

## Dependencies to other Devices, Servers, Programs, Components

None

## Direct Access Databases

| Host    | Type  | Database Name  | Used for                    |
| ------- | ----- | -------------- | --------------------------- |
| MongoDB | NOSQL | Users          | User management             |
| MongoDB | NOSQL | ActivityEvents | Storing all activity events |

## Exposed APIs

The full documentation of the APIs can be found [here](apis_server.md).

## Notes

For authentication the users credentials must be send in the request header.

## License

Private
