# CentOS

## Cron Service
- Task Scheduler in CentOS

### Edit cron job
`crontab -e`


https://crontab.guru/

### Restart cron 
`service crond restart`

## Deployment

#### Firewall
- Open Port `firewall-cmd --zone=public --add-port=XX/tcp --permanent`
- Reload firewall `firewall-cmd --reload`