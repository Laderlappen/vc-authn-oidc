# vc-authn-oidc

clone [traction](https://github.com/bcgov/traction)
connect those services to the network defined in by

adding the following to `<traction_folder>/scripts/docker-compose.yaml`

```
networks:
  default:
    external:
      name: oidc_vc_auth
```

`docker-compose up` from `<traction_folder>/scripts`

run `docker-compose up` from `demo/vue` of this project
run `docker-compose up` from `/script` of this project

### Prepare Acapy wallet for use

run `pip install requests` if needed.
run `python wallet_init.py` from `/scripts`

### Prepare controller for use

1. create default verification_configuration @`http://localhost:5201/docs#/ver_configs/create_ver_conf_ver_configs_post` execute that endpoint with default payload

### Prepare example wallet

You will need a digital wallet app with a credential that contains two attributes `first_name` and `last_name`
