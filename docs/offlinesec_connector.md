# offlinesec_connector script
The tool extracts data from SAP and request Offline Security Reports

0. Do not forget to set connection settings with [offlinsec_conn_settings](./offlinesec_conn_settings.md)

1. Set the request type with option '-r'. Now only "notes" is supported. Not required argument. 

2. Specify connection names and run the connector:
```sh
offlinesec_connector -c SY1 -c SY2
```

3. Specify group names and run the connector:
```sh
offlinesec_connector -g 'g:DEV' -g 'g:S4'
```

3. Set the group mode. There are two available options for argument:
* any - means all connections with specified groups (default)
* all - means only connections which contain all specified groups

4. Set SLA rules
```sh
offlinesec_connector -c SY1 -c SY2 -l "sla_rules_example.yaml"
```
An example of SLA rules file you can find [here](./sla_rules_example.yaml)

5. Set Exclude file
```sh
offlinesec_connector -c SY1 -c SY2 -e "exclusions_example.yaml"
```
An example of Exclusions file you can find [here](./exclusions_example.yaml)

6. Offline Security Client Check Variant
```sh
offlinesec_connector -c SY1 -c SY2 -v 1
```
please check [Offline Security Client Documentaion](https://github.com/offlinesec/offlinesec-client/blob/main/docs/how_to_prepare_sap_softs.md)

7. Delete temporary files
```sh
offlinesec_connector -c SY1 -c SY2 -d
```

8. Wait 5 minutes and get the report automatically
```sh
offlinesec_connector -c SY1 -c SY2 -w
```

9. Do not send the collected data to the server
```sh
offlinesec_connector -c SY1 -c SY2 --do-not-send
```
