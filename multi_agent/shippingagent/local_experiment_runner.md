

## Set service up:

```bash
python3 -m multi_agent.shippingagent.shippingagent_as_service
```

## Send a request to service:

``` bash

python3 -m multi_agent.shippingagent.client quote "1600 Amphitheatre Pkwy" "Mountain View" CA US 94043 3
python3 -m multi_agent.shippingagent.client ship  "1600 Amphitheatre Pkwy" "Mountain View" CA US 94043 3
```