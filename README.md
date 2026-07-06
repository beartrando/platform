Окружение для vaultwarden и wikijs
about website

docker compose up -d


docker run --rm \
-v ./services/certbot/conf:/etc/letsencrypt \
-v ./services/certbot/www:/var/www/certbot \
certbot/certbot certonly \
--webroot -w /var/www/certbot \
-d beartrando.org \
-d vaultwarden.beartrando.org \
-d wiki.beartrando.org \
-d mail.beartrando.org \
--email beartrando@gmail.com \
--agree-tos --no-eff-email \
--expand
