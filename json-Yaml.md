# JSON
- فرمت سبک برای انتقال دیتا است
- ربطی به زبان برنامه نویسی نداره
- خود توصیف کننده است
- برای ذخیره داده ها استفاده میشود
- و یک سینتکس است که جایگزین XML شد
- یک مدیا تایپ است

  ![image](https://github.com/milad6745/python/assets/113288076/97230845-d852-4629-a819-fefae149c751)

##  ِdiffrent between Python and Json
![image](https://github.com/milad6745/python/assets/113288076/88a1e0d2-ea63-429f-babe-bc931401d7c4)

## convert json to Dictionary and Dictionary to Json
```
import json

#convert dictionary to json
mydict =  {
    "name": "milad",
    "family": "baousi",
    "meli_code":"123456",
    "score":"50",
    "project":["DAM","zabbix"]
}
print (json.dumps(mydict))

#convert josn to dictionary
myjson = '{"name": "milad", "family": "baousi", "meli_code": "123456", "score": "50", "project": ["DAM", "zabbix"]}'
convert = json.loads(myjson)
print (convert)
```

# YAML
- یمل اومد که غالب پیچیده جیسون را ساده کنه
-  زبان data serializeation
-  مستقل از زبان است . language indipendent

## Rules o YAML
- casensitive
- extension .yaml or .yml
- tab doesnot support
- support -(hyphen) and space
- mix with json syntax

## why YAML
- kuber
- docker-compose
- Ansible
- Rancher
- Prometheus
- cloud-init
- Helm
- Envoy

## Yaml Syntax
![Capture1](https://github.com/milad6745/python/assets/113288076/a6278b27-5612-47b2-babe-ba306feeb16a)



## تبدیل جیسون به YAML


### Json Model
```
{
"name": "milad",
"family": "Baousi",
"score": 10,
"Class": ["Devops","Network"]
}
```
### YAML Model
```
name:milad
family:Baousi
score:10
class:
  - Devops
  - Network
```

### Example json to YAML
###JSON
```
[
 {
     "hosts": "all",
     "ignore_errors":"true",
     "tasks": [
         {
             "name": "update system",
             "apt": {
                 "update_cache": true,
                 "upgrade": true
             }
         }
     ]
 }
]
```
### YAML
```
---
- hosts: all
  ignore_errors: 'true'
  tasks:
  - name: update system
    apt:
      update_cache: true
      upgrade: true
```

| MARK | JSON   | YAML   |
| :---:   | :---: | :---: |
| { | {   |   |
| [ | [   |  - |
| " | " | |
| null | null | |

- نکته : در صورتی که به هر دلیل نیاز شد که از استرینگ در YAML هایمان استفاده کنیم بهترا تسک ه از فرمت استفاده کنیم

```
!!str string-value
```

### https://www.json2yaml.com/
![image](https://github.com/milad6745/python/assets/113288076/5317bd94-4167-46ab-a998-fcc95c4f89f1)

### example
```
{
  "message" : "Hello\niam milad baousi\ni 39 yeasr old."
  }
```
```
---
message: |-
  Hello
  iam milad baousi
  i 39 yeasr old.

```
### Yaml to Json

&default --> *default
expand karde
```
---
default_value: &default
 hostname: localhost
 port_number: 80
 

nginx_server: *default
apache_server: *default
```

```
{
  "default_value": {
    "hostname": "localhost",
    "port_number": 80
  },
  "nginx_server": {
    "hostname": "localhost",
    "port_number": 80
  },
  "apache_server": {
    "hostname": "localhost",
    "port_number": 80
  }
}
```


## Example
```
---
default_value: &default
 hostname: localhost
 port_number: 80
 

nginx_server:       
  <<: *default      # boro az default bekhon
  hostname: test    # badesh faghat hostesh ro change kon
```
```
{
  "default_value": {
    "hostname": "localhost",
    "port_number": 80
  },
  "nginx_server": {
    "hostname": "test",
    "port_number": 80
  }
}
```

## complex key
