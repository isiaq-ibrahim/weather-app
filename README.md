As part of my ongoing 20-day challenge to build one Python project a day, I’m thrilled to present my 8th project, a Weather App built with Python. The goal of this challenge is simple: to push myself daily, improve my Python skills, and build a solid portfolio of small but meaningful projects. In this project, I’ll take you through every step I followed to build this app, from library installation to writing and testing the code.

weather app python

If you're just getting started with Python and want to build something useful and fun, a weather app is a great mini-project. In this post, I’ll walk you through how I built a simple weather app that fetches real-time weather data using web scraping from Google search results. No API keys. No complicated setup. Just Python and a few lines of code!

## 📦 What You'll Need
Before we dive in, make sure you have the following Python libraries installed:

```python 
pip install requests beautifulsoup4
```
    
## The Complete Code
```python
import requests
from bs4 import BeautifulSoup

search = "Weather in Skopje"
url = f"https://www.google.com/search?&q={search}"

r = requests.get(url)

s = BeautifulSoup(r.text, "html.parser")

update = s.find("div", class_="BNEawe").text
print(update)
```

Here’s the code and a breakdown of how it works:

### 1. Import the Libraries

```python 
import requests
from bs4 import BeautifulSoup
```

- requests lets me send HTTP requests to websites.
- BeautifulSoup helps to parse and extract data from HTML

### 2. Define the Search Query
```python 
search = "Weather in Skopje"
```

I define the city I want weather data for. You can change "Skopje" to any city like "Weather in New York" or "Weather in Tokyo".

### 3. Build the Google Search URL

```python 
url = f"https://www.google.com/search?&q={search}"
```

This creates a URL that performs a Google search for the weather.

### 4. Send the Request

```python 
r = requests.get(url)
```

This line fetches the HTML content of the Google search results page.

### 5. Parse the HTML

```python 
s = BeautifulSoup(r.text, "html.parser")
```

I convert the HTML into a structured format using BeautifulSoup so I can search for specific elements.

### 6. Extract the Weather Info

```python
update = s.find("div", class_="BNEawe").text
```

Google displays the current temperature and weather inside a <div> tag with the class name BNEawe. This line finds that element and extracts the text (like 28°C).

### 7. Print the Result

```python 
print(update)
```

Finally, I print the weather update.


## Example Output

When you run the script, you might get something like:

```python 
26°C
```



## Conclusion
You’ve just built a simple weather app using Python, requests, and BeautifulSoup to scrape data directly from Google search. This is a great beginner project to practice web scraping and get comfortable with handling HTML in Python.



## ▶️ Demo Video


## ⚠️ A Word of Caution
Google’s page structure can change at any time, and this might break your script. This method is good for quick experiments but not recommended for production apps.

For more stable and legal use cases, consider using a free weather API like:
- OpenWeatherMap
- WeatherAPI
- Weatherstack











# 🌦️ Weather App in Python

This is a simple Python script that fetches the **current weather information** for any city or country by scraping Google Search results.

## 📌 Features

- Retrieves real-time weather data
- Lightweight and fast
- Uses Google search instead of relying on weather APIs
- Demonstrates the basics of web scraping

## 🧰 Technologies Used

- **Python 3**
- [`requests`](https://pypi.org/project/requests/): To send HTTP requests
- [`BeautifulSoup`](https://www.crummy.com/software/BeautifulSoup/): To parse and extract data from HTML

## 🚀 How It Works

1. The script constructs a Google search query like `"Weather in Skopje"`.
2. It sends a GET request to Google.
3. It uses BeautifulSoup to parse the HTML response.
4. It scrapes the div containing the weather data and prints the result.

## 🧪 Sample Code

```python
import requests
from bs4 import BeautifulSoup

search = "Weather in Skopje"
url = f"https://www.google.com/search?&q={search}"

r = requests.get(url)
s = BeautifulSoup(r.text, "html.parser")

update = s.find("div", class_="BNEawe").text
print(update)
```

## 📎 Note
- This script works well with basic weather queries on Google.
- It may break if Google updates its HTML structure.
- It's recommended for educational and personal use only, not production-level deployment.

📷 Output Example
```
21°C
```

#### ✅ Prerequisites
- Make sure you have the required libraries installed:
```bash
pip install requests beautifulsoup4
```

#### 🙌 Contributing

Feel free to fork the repository, submit pull requests, or suggest improvements!

#### 📄 License

This project is open source and available under the MIT License.
