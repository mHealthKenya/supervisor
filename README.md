# supervisor that runs c4c broadcast queues

start supervisor if .sock file cannot be found

cd /etc/supervisor
sudo supervisord
sudo supervisorctl restart all

start service
cd /etc/supervisor/conf.d
sudo supervisorctl start c4c-worker:*

To manually run queue
php artisan queue:work
