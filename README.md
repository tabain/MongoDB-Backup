# automatically-backup-MongoDB
mongodb, crontab, shell script, awscli, s3 
##  Make sure to:
 01) Name this file `backup.sh` and place it in `/home/ec2-user`
 02) `sudo yum install python`
 03) `curl -O https://bootstrap.pypa.io/get-pip.py`
 04) `python get-pip.py`
 05) `sudo  python get-pip.py`
 06) `curl "https://s3.amazonaws.com/aws-cli/awscli-bundle.zip" -o "awscli-bundle.zip"`
 07) `unzip awscli-bundle.zip`
 08) `sudo ./awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws`
 09) `/usr/local/bin/aws --version`
 10) `./awscli-bundle/install -h`
 11  `aws --version`
 11) Run `sudo apt-get install awscli` to install the AWSCLI
 12) Run `aws configure` (enter s3-authorized IAM user and specify region)
 13) Fill in DB host + name + port + user + password
 15) Create S3 bucket for the backups and fill it in below (set a lifecycle rule to expire files older than X days in the bucket)
 16) Run `sudo chmod +x backup.sh`
 17) Test it out via  `./backup.sh`
 18) Set up a daily backup at midnight via `crontab -e`:
    `0 0 * * * /home/ubuntu/backup.sh > /home/ubuntu/backup.log`
