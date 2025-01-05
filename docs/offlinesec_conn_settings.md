# offlinesec_conn_settings script
The tool manages connection settings for Offline Security Connector.  

1. Copy connection settings from the local file
```sh
offlinesec_conn_settings -f "sap_connections_example.yaml"
```
An example of connection file is available [here](./sap_connections_example.yaml)
Please refer to [the pyrfc documentation](https://github.com/SAP-archive/PyRFC/blob/main/doc/authentication.rst) to check what options you need to set in your case

2. Delete connections by connection name
```sh
offlinesec_conn_settings -d SY1 -d SY2
```
SY1 and SY2 - connection names

3. Print all current connection settings
```sh
offlinesec_conn_settings -l
```

4. Delete password for connection from keyring db
```sh
offlinesec_conn_settings -p SY1
```
New password will be set during next connection attempt