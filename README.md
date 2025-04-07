##
1. Cloudflare, create a token for ddns, and set a record as `vpn` point to `your public ip address`
2. Clone repo to root, `cp cloudflare-template.sh cloudflare.sh`
3. set for
     ```
    auth_email=""                                       # The email used to login 'https://dash.cloudflare.com'
    auth_method="token"                                 # Set to "global" for Global API Key or "token" for Scoped API Token
    auth_key=""                                         # Your API Token or Global API Key
    zone_identifier=""                                  # Can be found in the "Overview" tab of your domain
    record_name="" 
    ```
4. execute to test
5. set cron job, `crontab -e` set as `*/1 * * * * /bin/bash /root/cloudflare-ddns-updater/cloudflare.sh`
6. restart cron `systemctl restart cron`





## Installation

```bash
git clone https://github.com/K0p1-Git/cloudflare-ddns-updater.git
```

## Usage
This script is used with crontab. Specify the frequency of execution through crontab.

```bash
# ┌───────────── minute (0 - 59)
# │ ┌───────────── hour (0 - 23)
# │ │ ┌───────────── day of the month (1 - 31)
# │ │ │ ┌───────────── month (1 - 12)
# │ │ │ │ ┌───────────── day of the week (0 - 6) (Sunday to Saturday 7 is also Sunday on some systems)
# │ │ │ │ │ ┌───────────── command to issue                               
# │ │ │ │ │ │
# │ │ │ │ │ │
# * * * * * /bin/bash {Location of the script}
```

## Tested Environments:
macOS Mojave version 10.14.6 (x86_64) <br />
AlmaLinux 9.3 (Linux kernel: 5.14.0 | x86_64) <br />
Debian Bullseye 11 (Linux kernel: 6.1.28 | aarch64) <br />

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## Reference
This script was made with reference from [Keld Norman](https://www.youtube.com/watch?v=vSIBkH7sxos) video.

## License
[MIT](https://github.com/K0p1-Git/cloudflare-ddns-updater/blob/main/LICENSE)
