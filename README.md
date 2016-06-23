Minimalist "Store" for snaps.

Edit /etc/environment, add

```
SNAPPY_FORCE_CPI_URL=http://localhost:5000/api/v1/
```

Then bounce snapd

```
sudo service snapd restart
```

Put snaps (named as name.snap) and metadata (named as name.meta) in files/

Setup virtualenv

```
virtualenv env
. env/bin/activate
pip install -r requirements.txt
```

Run it

```
python store.py
```

Supports snap find <name>, snap install <name>

```
snap find foobar25
sudo snap install foobar25
```

Notes: at the moment this has to be run on the same host as snapd is
installed since the download URLs are hardcoded in the metadata.
