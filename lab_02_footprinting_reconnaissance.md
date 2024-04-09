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

## Lab 04 - Perform website Footprinting

### Task 1 Gather information about a target website using ping command line utility

```bash
ping www.certifiedhacker.com

# finding maximum frame size
ping www.certifiedhacker.com -f -l 1500

# if response is "Packet needs to be fragmented but DF set" type:
ping www.certifiedhacker.com -f -l 1300

# if response is positive try different values between 1300 and 1500
ping www.certifiedhacker.com -f -l 1472

# ----------------------------
# discover what happens when Time to Live (TTL) expires
ping www.certifiedhacker.com -i 3

# try
ping www.certifiedhacker.com -i 2 -n 1

# then
ping www.certifiedhacker.com -i 3 -n 1

# this work for me (at office)
ping www.certifiedhacker.com -i 8 -n 1

```

### Task 2 Gather information about a Target website using website informer

> [https://website.informer.com](https://website.informer.com)

Type the URL of website and click Search

The search result contains information such as General info, Stats & Details and IP Whois

Other tools:

- Burp suite
- Zaproxy

### Task 3 Extract a Company's data using Web data extractor

> [http://www.webextractor.com/](http://www.webextractor.com/)

... is a software for windows

- click New
- type the Starting URL
- check all options
- click Ok
- click Start

... will start collecting information


### Task 4 Mirror a Target website using HTTrack Web Site Copier

... is a software

### Task 5 Gather a Wordlist from the Target Website using cewl

cewl is a Ruby app [https://github.com/digininja/CeWL](https://github.com/digininja/CeWL).

```bash
# -d represent the depth to spider the website and -m represents minimum word length
cewl -d 2 -m 5 www.erdis.it

# the command returns a unique wordlist from the target website is gathered

# you can save the wordlist on a text file
cewl -w wordlist.txt -d 2 -m 5 www.erdis.it
```

## Lab 05 - Perform Email Footprinting

### Task 1 Gather information about a target by tracing emails using eMailTrackerPro

... is a professional software

Other tools:

- Infoga
- Mailtrack

## Lab 06 - Perform Whois Footprinting

### Task 1 Perform Whois Lookup using DomainTools

> [http://whois.domaintools.com](http://whois.domaintools.com)
