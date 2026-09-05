Окружение для vaultwarden и wikijs
about website

docker compose up -d


docker run --rm \
-v ./services/certbot/conf:/etc/letsencrypt \
-v ./services/certbot/www:/var/www/certbot \
certbot/certbot certonly \
--webroot -w /var/www/certbot \
-d beartrando.org \
-d vault.beartrando.org \
-d wiki.beartrando.org \
-d mail.beartrando.org \
-d tiny.beartrando.org \
-d vipp.beartrando.org \
--email beartrando@gmail.com \
--agree-tos --no-eff-email \
--expand



bw config server https://vault.beartrando.org
bw login
bw unlock
bw list items < ~/.bw-password > backup-items.json
