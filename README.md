## Tool that helps more easier run apps in AWS Device Farm

##### Description
Did you try to run an app in AWS Device Farm via CLI or API? It was easy, right? Right now you can probably say ARN of your project after wake up in the middle of night.    
This tool helps to run apps in AWS Device Farm easier. You don't need to know ARN, because it's for machine, not for people.

##### AWS Credentials

Set environment variables     
```
export AWS_ACCESS_KEY_ID=<key>    
export AWS_SECRET_ACCESS_KEY=<secret>
```     

##### Running
Get it via    
``` 
go get github.com/artemnikitin/devicefarm-ci-tool 
``` 
   
Required launch parameters:   
```
devicefarm-ci-tool -project=name -app=/path/to/my/app.apk
```

Additional optional parameters:   
- ```region``` set S3 region, by default region will be set to ```us-west-2```(At this moment, will be set to ```us-west-2``` in any case, because it's only supported region for the moment)          
Example:    
``` 
devicefarm-ci-tool -project=name -app=/path/to/my/app.apk -region=region-name 
```    
- ```devices``` specify name of device pool where app will be run      
Example:   
``` 
devicefarm-ci-tool -project=name -app=/path/to/my/app.apk -devices=my-device-pool
```   
- ```config``` specify path to config in JSON format      
Example:   
``` 
devicefarm-ci-tool -project=name -app=/path/to/my/app.apk -config=/path/to/config.json
```   
- ```wait``` will wait for end of run. Disabled by default. Useful for CI.     
Example:   
``` 
devicefarm-ci-tool -project=name -app=/path/to/my/app.apk -wait=true
```   

You can specify parameter ```-log=true``` for logging AWS requests and responses.

##### TODO  
1. Code cleanup
2. Fix issues
3. Alternative ways to authenticate in AWS
