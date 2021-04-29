



<cloudwatch-agent-w11-d1.png>


aws ssm send-command 
  --document-name "AWS-ConfigureAWSPackage" 
  --document-version "1" 
  --targets '[{"Key":"InstanceIds","Values":["i-0e4b1c6209e50ecbb"]}]' 
  --parameters '{"action":["Install"],"installationType":["Uninstall and reinstall"],"version":["latest"],"additionalArguments":["{}"],"name":["AmazonCloudWatchAgent"]}' 
  --timeout-seconds 600 
  --max-concurrency "50" 
  --max-errors "0" 
  --region us-west-2
  
  
  
  
## Parameter Store 

* Value 

```JSON
{
  "logs": {
    "logs_collected": {
      "files": {
        "collect_list": [
          {
            "log_group_name": "HttpAccessLog",
            "file_path": "/var/log/httpd/access_log",
            "log_stream_name": "{instance_id}",
            "timestamp_format": "%b %d %H:%M:%S"
          },
          {
            "log_group_name": "HttpErrorLog",
            "file_path": "/var/log/httpd/error_log",
            "log_stream_name": "{instance_id}",
            "timestamp_format": "%b %d %H:%M:%S"
          }
        ]
      }
    }
  },
  "metrics": {
    "metrics_collected": {
      "cpu": {
        "measurement": [
          "cpu_usage_idle",
          "cpu_usage_iowait",
          "cpu_usage_user",
          "cpu_usage_system"
        ],
        "metrics_collection_interval": 10,
        "totalcpu": false
      },
      "disk": {
        "measurement": [
          "used_percent",
          "inodes_free"
        ],
        "metrics_collection_interval": 10,
        "resources": [
          "*"
        ]
      },
      "diskio": {
        "measurement": [
          "io_time"
        ],
        "metrics_collection_interval": 10,
        "resources": [
          "*"
        ]
      },
      "mem": {
        "measurement": [
          "mem_used_percent"
        ],
        "metrics_collection_interval": 10
      },
      "swap": {
        "measurement": [
          "swap_used_percent"
        ],
        "metrics_collection_interval": 10
      }
    }
  }
}
```

# CloudWatch Logs

<cloudwatch-logs.png>

The Web Server generates two types of log data:

* Access Logs
* Error Logs

#CloudWatch Metricx

<cloudwatch-metrics.png>


# CloudWatch Events 

<cloudwatch-events.png>
