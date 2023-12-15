# Cryptocurrency-Website-API


```python
!pip install requests

```


```python
import requests

# List of cryptocurrency-related website URLs
crypto_websites = [
    "https://www.coindesk.com/",
    "https://coinmarketcap.com/",
    "https://cointelegraph.com/",
    # ... add more URLs here
]

# Common headers or parameters for all requests
headers = {"Authorization": "Bearer YOUR_API_KEY"}
params = {"param1": "value1", "param2": "value2"}

for url in crypto_websites:
    try:
        # Make a GET request
        response = requests.get(url, headers=headers, params=params)

        # Check if the request was successful (status code 200)
        if response.status_code == 200:
            data = response.json()  # Parse JSON response
            print(f"Data from {url}: {data}")
        else:
            print(f"Error for {url}: {response.status_code} - {response.text}")

    except Exception as e:
        print(f"Error for {url}: {e}")


```
