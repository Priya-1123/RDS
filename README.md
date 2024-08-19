# RDS
--------------------------------------------------------
**How to take a dump of rds:**

mysqldump -h <end point of rds> -u <username of rds> -p backupfile name>backupfile name.sql

passphrase= asm gpg key ( retrived secrete key)

echo $passphrase

gpg -c --passphrase $passphrase --batch --yes -o backupfile.sql.gpg backup file.sql

aws s3 cp backupfile.sql.gpg <s3 path>
 
******************Detailed Steps:**********************************************

**Connect to RDS Instance:**
Run mysqldump command to create a dump of the RDS instance. Replace <RDS Endpoint>, <RDS Username>, and <BackupFileName> with your specific values. The -p flag will prompt for the password.
C: mysqldump -h <end point of rds> -u <username of rds> -p backupfile name>backupfile name.sql

**Retrieve Passphrase:**
Retrieve the passphrase used for encryption. Ensure it is stored securely and retrieved correctly.
C: passphrase= asm gpg key ( retrived secrete key)

**Encrypt SQL Dump File:**
Use gpg to encrypt the SQL dump file. The --batch and --yes options allow automatic processing and non-interactive mode, suitable for scripts.
C: gpg -c --passphrase $passphrase --batch --yes -o backupfile.sql.gpg backup file.sql

**Upload Encrypted File to AWS S3:**
Use aws s3 cp to upload the encrypted file to your spe:ified S3 bucket path.
C: aws s3 cp backupfile.sql.gpg <s3 path>

Ensure you have the necessary permissions and tools (e.g., mysqldump, gpg, aws cli) installed and configured before running these commands.
