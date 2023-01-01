# Success

When an API call is successful, the Plea object is used as a simple envelope for the results, using the data key, as in the following.

{% code title="GET /posts" %}
```json
{
	"status": "success",
	"metadata": {
		"cid": "e1f1f580-eaad-4de4-a354-bf017b0f7617",
		"language": "en-US"
	},
	"data": [
		{
			"id": 1,
			"title": "Post 1",
			"body": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."
		},
		{
			"id": 2,
			"title": "Post 2",
			"body": "Id cursus metus aliquam eleifend mi in nulla."
		},
		{
			"id": 3,
			"title": "Post 3",
			"body": "Elit ut aliquam purus sit amet luctus venenatis."
		}
	]
}
```
{% endcode %}

{% code title="GET /posts/1" %}
```json
{
	"status": "success",
	"metadata": {
		"cid": "f9fed10a-a889-49e0-92c5-11fc68009217",
		"language": "en-US"
	},
	"data": {
		"id": 1,
		"title": "Post 1",
		"body": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."
	}
}
```
{% endcode %}
