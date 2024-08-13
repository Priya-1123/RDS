# RDS
--------------------------------------------------------
how to take dump of rds:

mysqldump -h <end point of rds> -u <username of rds> -p backupfile name>backupfile name.sql

passphrase= asm gpg key ( retrived secrete key)

echo $passphrase

gpg -c --passphrase $passphrase --batch --yes -o backupfile.sql.gpg backup file.sql

aws s3 cp backupfile.sql.gpg <s3 path>
 
