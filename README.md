# bash-backup-script
A simple bash script to create backups with timestamps

# Bash Backup Script

This script performs backups of specified directories.

## Script Code:

```bash
#!/bin/bash

# Backup Script
# Usage: ./backup.sh /path/to/backup

SOURCE_DIR=$1
BACKUP_DIR="/path/to/backup/destination"

if [ ! -d "$SOURCE_DIR" ]; then
    echo "Source directory does not exist!"
    exit 1
fi

# Create backup
TIMESTAMP=$(date +%Y%m%d%H%M%S)
BACKUP_FILE="$BACKUP_DIR/backup_$TIMESTAMP.tar.gz"

echo "Creating backup..."
tar -czf "$BACKUP_FILE" "$SOURCE_DIR"

echo "Backup completed: $BACKUP_FILE"
