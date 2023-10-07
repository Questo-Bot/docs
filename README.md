---
description: Documentation for Questo API.
---

# Get Started

{% hint style="info" %}
The base API URL for all endpoints is [Questo API](http://127.0.0.1:5000/o/0wjTQHHAc5FD1hLLjKzh/s/n02O2YZqHuM2gq6Gb9FZ/ "mention")
{% endhint %}

{% hint style="warning" %}
A token is required
{% endhint %}

## Introduction

This line imports the `requests` library, which is needed for making HTTP requests in Python.

```python
pip install requests
```

## Define the URL

Replace `"https://api.example.com/data"` with the actual URL you want to make the GET request to.

<pre class="language-python"><code class="lang-python"><strong>url = "https://api.example.com/data"
</strong></code></pre>

## Define the API Key

Replace `"YOUR_API_KEY"` with your actual API key. This is the authentication token you'll use to authenticate your requests.

```python
api_key = "YOUR_API_KEY"
```

## Define Additional Parameters (Optional)

You can include additional parameters in the `params` dictionary if your API endpoint requires them. Replace `"param1"`, `"value1"`, `"param2"`, and `"value2"` with your specific parameter names and values.

```python
params = {
    "param1": "value1",
    "param2": "value2"
}
```

## Create Headers with Authentication

This line creates the headers for the HTTP request. The `"Authorization"` header is set with the value `"Bearer YOUR_API_KEY"` where `YOUR_API_KEY` is replaced with the actual API key.

```python
headers = {
    "Authorization": f"Bearer {api_key}"
}
```

## Make the HTTP GET Request

This line sends the HTTP GET request to the specified URL (`url`) with the provided additional parameters (`params`) and headers containing the API key (`headers`). The response from the server is stored in the `response` variable.

```python
response = requests.get(url, params=params, headers=headers)
```

## Handle the Response

This part checks the HTTP status code of the response. If the status code is `200` (which means the request was successful), it prints the response content using `response.text`. If the status code is different from `200`, it prints an error message along with the status code.

```python
if response.status_code == 200:
    print("Response content:", response.text)
else:
    print("Error:", response.status_code)
```
