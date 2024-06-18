# Bash

```
echo ""; while read -r line; do cname_record=$(dig +short @8.8.8.8 $line CNAME); if [[ -n "$cname_record" ]]; then if [[ "$cname_record" == "yourdomain.com." ]]; then echo -e "\033[32m[+] $line\033[0m"; else echo "\033[31m[-] $line -> CNAME of $cname_record\033[0m"; fi; else echo -e "\033[34m[*] $line -> No CNAME\033[0m"; fi; done < subdomains.txt
```
