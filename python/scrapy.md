## env install
### debian
1. install python3
   `sudo apt-get install python3 python3-dev python3-pip libxml2-dev libxslt1-dev zlib1g-dev libffi-dev libssl-dev`
2. install python venv
   `sudo apt-get install python3-venv`
3. create virtual python env
   `python3 -m venv scrapy-env`
4. use virtual env
   `source ./scrapy-env/bin/activate`
5. deactivate virtual env
   `deactivate`
6. install python scarpy
   `python -m pip install scrapy`
7. 
   
| field      | description                 |
| ---------- | --------------------------- |
| start_urls | request urls define (array) |
| parse      | default callback (function) |

