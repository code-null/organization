# Delta Omega

**Note:** This project follows the [code null guidelines](https://github.com/code-null/organization/blob/main/guidelines.md) in version v2.0.0.0

A small home server to monitor temperature and humidity. It also provides an interfaces to view these records.

## Status

Status: Offline

Latest Stable Version: 1.4.2.0

## Technical Details

| Segment | Device Type    | Technical ID | Public ID | Official Name | Type   | Requires Accounts | Technology | Versioning                                   |
| ------- | -------------- | ------------ | --------- | ------------- | ------ | ----------------- | ---------- | -------------------------------------------- |
| Device  | Raspberry Pi 4 | DZTDI        | codnRaspi | Delta Omega   | manage | false             | NodeJS     | [CNV 1.0.0.0](../resources/cn_versioning.md) |

## Dependencies to connected Hardware, Sensors, other Devices, Servers, Programs, Components

| Name                                    | Needed for       |
| --------------------------------------- | ---------------- |
| [DHT22](https://learn.adafruit.com/dht) | Reading air data |

## Direct Access Databases

| Host    | Type  | Database Name   | Used for                           |
| ------- | ----- | --------------- | ---------------------------------- |
| MongoDB | NOSQL | HomeEnvironment | Recording temperature and humidity |

## Exposed APIs

| Endpoint  | Type | Description                                        | Expects | Returns                                             |
| --------- | ---- | -------------------------------------------------- | ------- | --------------------------------------------------- |
| /air-data | GET  | Displays a table of air data for the last 12 hours | none    | {time: date, temperature: string, humidity: string} |

## Notes

This device can only be reached from within the locale network.

## License

None
