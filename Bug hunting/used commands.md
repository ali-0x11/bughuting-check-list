## ffuf

```
ffuf -u W1/W2 -w live_domains.txt:W1 -w /usr/share/wordlists/seclists/Discovery/Web-Content/big.txt:W2 -o output_xaa -H 'User-Agent : Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.' -mc 200 -c
```

## python

```
virtualenv -p python3 .venv
```

```
source .venv/bin/activate
```

## httpx

```
httpx -l all.txt -o live_domains.txt -random-agent -threads 300
```


## subfinder

```
subfinder -d giphy.com -all -oD subfinder_recon
```

```
subfinder -dL giphy.com -all -oD subfinder_recon
```

## nuclei

```
nuclei -o output.txt -bs <> -c <> -rl <>
```

## grep

```
grep -rnw . -e 'CVE-2023-24044'
```

## katana

```
katana -list private_live.txt -jc -kf -ef jpg,jpeg,gif,css,tif,tiff,png,ttf,woff,woff2,ico,svg -c 50 -p 50 -rl 750 -o katana_output.txt -nc | tee -a katana_output_1.txt
```
