# LAB 02 - Footprinting and Reconnaissance

## Lab 1 - Perform Footprinting through search engines

### Task 1 Gather information using advanced Google hacking techniques

- on google.com type **intitle:password site:www.eccouncil.org** and press Enter
- on google.com type **EC-Council filetype:pdf** and press Enter

You can also use the following operators:

- cache
- allinurl
- inurl
- allintitle
- inanchor
- allinanchor
- link
- related
- info
- location

### Task 2 Gather information from video search engines

- on youtube.com search type the name of your target organization. From any video in the results pages **Copy link location** from the contextual menu
- paste the link on [https://citizenevidence.amnestyusa.org/](https://citizenevidence.amnestyusa.org/) search

### Task 3 Gather information from FTP search engine

- on [https://www.searchftps.net/](https://www.searchftps.net/) type microsoft and click Search

Others:

- globalfilesearch.com (NOT secure for Microsoft Defender)
- [freewareweb.com](freewareweb.com)

### Task 4 Gather information from IoT search engines

- on [www.shodan.io](www.shodan.io) search amazon. You will obtain the search results with the details of all the vulnerable IoT devices related to amazon in various countries.

## Lab 02 - Perform Footprinting through web services

### Task 1 Find the company's domains and sub-domains using Netcraft

> [www.netcraft.com](www.netcraft.com)

- click Resources -> Research Tools -> Site report
- type the target website's URL and press "Look up"
- in the Network section, click on the website link in the Domain field to view the subdomains

Others:

- Sublist3r
- Pentest-Tools Find Subdomains on [pentest-tools.com](pentest-tools.com)

### Task 2 Gather personal information using PeekYou online people search engine

> [www.peekyou.com](www.peekyou.com)

Others:

- pipl
- intelius
- beenVerified

### Task 3 Gather an Email List using theHarvester

```bash

sudo theHarvester -d microsoft.com -l 200 -b baidu
# -d specifies the domain or company name to search
# -l specifies the number of results
# -b specifies the data source
```

theHarvester starts extracting the details and displays them on the screen

### Task 4 Gather information using Deep and Dark web searching

- install Tor Browser
- Connect to Tor
- search "hacker for hire" on google.com and on Tor
- change country of VPN/Proxy on Tor

On Tor, you can use also:

- The Hidden Wiki
- FakeID
- The Paypal Cent

### Task 5 Determine target OS through passive footprint

> [https://search.censys.io/](https://search.censys.io/)

## Lab 03 - Perform footprinting through social networking sites

### Task 1 Gather employees' information from Linkedin using theHarverster

```bash
sudo theHarvester -d eccouncil -l 200 -b linkedin
# Linkedin returns [!] Invalid source.
```

### Task 2 Gather personal information from various social networking sites using Sherlock

```bash
git clone https://github.com/sherlock-project/sherlock.git

pip install -r requirements.txt

python3 sherlock.py satya nadella
```

Other:

- Social searcher
- UserRecon

### Task 3 Gather information using Followerwonk

> [https://followerwonk.com/analyze](https://followerwonk.com/analyze)
