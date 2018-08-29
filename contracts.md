# Contracts

{% api-method method="post" host="https://${host}" path="/api/0.1/contracts" %}
{% api-method-summary %}
Create
{% endapi-method-summary %}

{% api-method-description %}
Create a new contract.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="asset" type="string" required=true %}
The asset the contract represents.
{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="string" required=true %}
The amount of tokens to allocate on contract creation. There cannot be more tokens of the asset than the contract amount.
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="string" required=false %}
If upserting, the ID of the contract. Some node operators do not allow upserting a contract.
{% endapi-method-parameter %}

{% api-method-parameter name="transfers" type="array" required=false %}
A list of transactions allocating tokens to be executed on contract creation.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "name": "Cake's name",
    "recipe": "Cake's recipe name",
    "cake": "Binary cake"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "message": "Ain't no cake like that."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



