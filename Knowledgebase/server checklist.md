
rsync -avh --progress root@10.117.117.253:/mnt/DataPool/ /fastpool/migration_backup/DataPool/


| source               | target                             | check |     |
| -------------------- | ---------------------------------- | ----- | --- |
| 10.117.117.253 (TNS) | 10.117.117.197 (PVE)               |       |     |
| /mnt/DataPool/       | /fastpool/DataPool/                |       |     |
| ../data/             | ../data/                           | X     |     |
| ../documents/        | ../documents/                      | X     |     |
| ../exchange/         | ../exchange/                       | X     |     |
| ../music/            | ../music/                          | X     |     |
| ../photos/           | ../photos/                         | X     |     |
| ../testsmb/          | ../testsmb/                        | -     |     |
| ../video/            | ../video/                          |       |     |
| ..../diving/         | ..../diving/                       | X     |     |
| ..../dokus/          | ..../dokus/                        | X     |     |
| ..../movies/         | ..../movies/                       | X     |     |
|                      |                                    |       |     |
|                      | 10.117.117.100                     |       |     |
| ..../series/         | /tempbackup/DataPool/video/series/ |       |     |
| /mnt/DataPoolNVME/   | /DataPoolNVME/                     |       |     |
|                      |                                    |       |     |
