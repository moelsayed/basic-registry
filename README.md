# Basic Registry

Very simple private registry with ssl support to simplify testing.

To run:
  - Point a domain name to the IP of the machine running this
  - Run the following commands:
  ```  
  $ cat certificate.crt certificate_chain.crt > nginx_config/domain.crt
  $ cat certificate.key > nginx_config/domain.key
  $ docker-compose up
  ```

Tag/push/pull your images at will, no auth required!


### Adding basic auth
- Uncomment the basic auth related lines in nginx_config/nginx.conf
- Run the following command: 
  ```
  $ docker run --rm -ti melsayed/htpasswd <username> <password> >>  nginx_config/registry.password
  ```
  
Based on: https://www.digitalocean.com/community/tutorials/how-to-set-up-a-private-docker-registry-on-ubuntu-14-04
