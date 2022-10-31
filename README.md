<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1" />

    <title>REPL</title>

    <link rel="icon" type="image/png" href="favicon.png" />
    <link rel="stylesheet" href="https://pyscript.net/latest/pyscript.css" />
    <script defer src="https://pyscript.net/latest/pyscript.js"></script>
  </head>
  
  <py-env>
      - requests
      - BeautifulSoup
  </py-env>
  
  <body>
    Hello world! <br>
    This is the current date and time, as computed by Python:
    <py-script>
import requests
from bs4 import BeautifulSoup
  
url = 'https://jovempan.com.br/noticias'
response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')

headlines = soup.find_all('h2', attrs={'class':'post-title'})
 
print("Noticias : Jovem Pan")
print("")
for x in headlines:
    print(x.text.strip())
    print("")
    </py-script>
  </body>
</html>
