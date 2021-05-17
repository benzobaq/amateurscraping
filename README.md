# amateurscraping

from bs4 import BeautifulSoup
from urllib.request import urlopen

url = "https://www.celestrak.com/NORAD/elements/tle-new.txt"
r = requests.get(url, allow_redirects=True)
open('30 days.txt', 'wb').write(r.content)
page = urlopen(url)
html = page.read().decode("utf-8")
soup = BeautifulSoup(html, "html.parser")
print(soup.get_text())
