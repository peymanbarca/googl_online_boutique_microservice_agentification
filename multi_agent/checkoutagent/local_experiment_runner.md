

## Set service up:

```bash
python3 -m multi_agent.checkoutagent.checkoutagent_as_service
```

## Send a request to service:

``` bash

python3 -m multi_agent.checkoutagent.client_cart
python3 -m multi_agent.checkoutagent.client 1 USD "1600 Amphitheatre Pkwy" "Mountain View" CA US 94043 test@example.com 4111111111111111 123 2030 1
python3 -m multi_agent.checkoutagent.client 1 USD "1600 Amphitheatre Pkwy" "Mountain View" CA US 94043 test@example.com 4111111111111111 123 2025 1
```