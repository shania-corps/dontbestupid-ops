# FIRST TIME

docker-compose run --rm letsencrypt \
  letsencrypt certonly --webroot \
  --email vix.andrade21@gmail.com --agree-tos \
  -w /var/www/letsencrypt -d dagobah.vixandrade.xyz

# THEN

docker-compose kill -s SIGHUP nginx

# RENEWAL

docker-compose run --rm letsencrypt letsencrypt renew