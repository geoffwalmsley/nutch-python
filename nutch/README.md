Crawl.py Usage Guide and Examples
================================

## 1. Create new config

```
$ ./crawl.py create conf -h
usage: crawl.py create conf [-h] -cf CONF_FILE -id ID

optional arguments:
  -h, --help            show this help message and exit
  -cf CONF_FILE, --conf-file CONF_FILE
                        Path to conf file, nutch-site.xml
  -id ID, --id ID       Id for config

```

### Example:

`./crawl.py create conf -cf ../conf/nutch-site.xml -id 'conf3'`
    

# 2. Run crawl for n rounds

```
$ ./crawl.py crawl -h
usage: crawl.py crawl [-h] -ci CONF_ID -n NUM_ROUNDS

optional arguments:
  -h, --help            show this help message and exit
  -sf SEED_FILE, --seed-file SEED_FILE
                        Seed file path (local path)
  -ci CONF_ID, --conf-id CONF_ID
                        Config Identifier
  -n NUM_ROUNDS, --num-rounds NUM_ROUNDS
                        Number of rounds/iterations
                        
$ ./crawl.py crawl seed -h
usage: crawl.py crawl seed [-h] [-sf SEED_FILE] [-sl SEED_LIST]

optional arguments:
  -h, --help            show this help message and exit
  -sf SEED_FILE, --seed-file SEED_FILE
                        Seed file path (local path)
  -sl SEED_LIST, --seed-list SEED_LIST
                        Comma separated set of seeds to crawl
```

### Example
    
To run two rounds:

`./crawl.py crawl seed --seed-file ../seed/urls.txt --conf-id conf3 -n 2`
    

# 3. Specify Nutch server URL 
```
$ ./crawl.py -h
usage: crawl.py [-h] [-u URL] {create,crawl} ...

Nutch Rest Client CLI

positional arguments:
  {create,crawl}     sub-commands
    create           command for creating seed/config
    crawl            Runs Crawl

optional arguments:
  -h, --help         show this help message and exit
  -u URL, --url URL  Nutch Server URL
```

## Example :

   `./crawl.py -u http://remotehost:8080/ crawl|create`

# 4. Specify Seeds from the Command Line Arguments
```
$ ./crawl.py crawl seed -h
usage: crawl.py crawl seed [-h] [-sf SEED_FILE] [-sl SEED_LIST]

optional arguments:
  -h, --help            show this help message and exit
  -sf SEED_FILE, --seed-file SEED_FILE
                        Seed file path (local path)
  -sl SEED_LIST, --seed-list SEED_LIST
                        Comma separated set of seeds to crawl
```

## Example :
```
$ ./crawl.py crawl -ci default -n 1 seed -sl "http://www.google.com"
```
   
