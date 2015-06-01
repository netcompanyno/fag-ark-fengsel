# fag-ark-fengsel

Repo for å orkestrere fengselscaset.

## Docker Compose

Docker Compose kan brukes for å ta opp og ned Docker containere med de ulike tjenestene.
F.eks:

`docker-compose up -d`

Ta bort `-d` for å kjøre i forgrunnen. Legg på navn på en tjeneste for å kun ta opp den tjenesten.

## Windows

Docker Compose virker ikke på Windows. Så det enkleste er å kjøre Docker Compose inne i en egen Docker container.

Legg til et alias i `.bashrc`:

`alias dc='docker run -v /$(pwd):/app -v //var/run/docker.sock:/var/run/docker.sock dduportal/docker-compose:latest'`

Clone dette repoet, og gå inn i mappen etterpå. Kjør så:

`dc up -d`

Det `dc` gjør er å eksponere mappen du er i til Docker Compose containeren, slik at den kan utføre kommandoer mot configen i lokalt utsjekket `docker-compose.yml`. 
