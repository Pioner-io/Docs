# Front-end Calls

Each second an RFQ based on the last input from the parameter input in the frontend is triggered. In response, the front end receives all the inputs to display or interact with the contracts in 1 click.

{% swagger method="post" path="" baseUrl="https://api.pioner.io/get-account-data" summary="" %}
{% swagger-description %}
{ "asset1": "BTC", "asset2": "USDC", "address": "0x123", "qty": 100, "leverage": 2 }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}
{% endswagger %}

