## Set up Monitoring
Everything is stored here for the monitoring system.

To install the namespace. 

`kubectl create namespace monitoring`

For installation prometheus, writing comand.

`helm install prometheus-operator -f values.yaml stable/prometheus-operator  --namespace monitoring`

### Support for notification channels
 1. DingDing
 2. Discord
 3. Email
 4. Google Hangouts Cha
 5. Hipchat
 6. Kafka
 7. Line
 8. Microsoft Teams
 9. OpsGenie
 10. Pagerduty
 11. Prometheus Alertmanager 
 12. Pushover
 13. Sensu
 14. Slack
 15. Telegram
 16. Threema
 17. VictorOps
 18. Webhook
 19. Zenduty

