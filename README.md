# lookup names from csv in ServiceNow CMDB with powershell

```
$cmdb_names = @(
'hostname',
'itemname'
)

$cmdb_names
$Global:snow_url = "https://YOURTENANT.service-now.com/now/nav/ui/classic/params/target/cmdb_ci_list.do%3Fsysparm_query%3D"+$cmdb_names[0]
    foreach ($cmdb_name in $cmdb_names) {
    $Global:snow_url += "%255EORnameSTARTSWITH"+$cmdb_name
}

start $Global:snow_url
```
