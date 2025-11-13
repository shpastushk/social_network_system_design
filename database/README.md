Медиаданные храним в s3 storage.

Расчет дисков

- Реакции

Capacity <br>
Per year = 12кб/с * 86400 * 365 = 378Гб <br>
IOPS = 57870 <br>
Throughput = 382 кб/с

HDD <br>
IOPS (600) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во HDD = 600

SSD (SATA) <br>
IOPS (60) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во SSD (SATA) = 60

SSD (nVME) <br>
IOPS (6) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во SSD (nVME) = 6 <br>

Используем диски SSD (SATA) = 60 <br>

- Комментарии

Capacity <br>
Per year = 116кб/с * 86400 * 365 = 3.7Тб <br>
IOPS = 232638 <br>
Throughput = 23 мб/с

HDD <br>
IOPS (2327) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во HDD = 2327

SSD (SATA) <br>
IOPS (233) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во SSD (SATA) = 233 <br>

SSD (nVME) <br>
IOPS (24) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во SSD (nVME) = 24

Используем диски SSD (SATA) = 233 <br>

- Посты

Capacity <br>
Per year = 13 кб/с * 86400 * 365 = 410Гб <br>
IOPS = 23264 <br>
Throughput = 25 мб/с

HDD <br>
IOPS (233) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во HDD = 233

SSD (SATA) <br>
IOPS (24) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во SSD (SATA) = 24

SSD (nVME) <br>
IOPS (3) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во SSD (nVME) = 1

Используем диски SSD (SATA) = 24 <br>

- Медиаданные

Capacity <br>
Per year = 566 кб/с * 86400 * 365 = 18Тб <br>
IOPS = 23264 <br>
Throughput = 114 мб/с

HDD <br>
IOPS (233) <br>
Throughput (2) <br>
Capacity (1) <br>
Кол-во HDD = 233

SSD (SATA) <br>
IOPS (24) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во SSD (SATA) = 24

SSD (nVME) <br>
IOPS (3) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во SSD (nVME) = 1

Используем диски SSD (SATA) = 24 <br>

- Подписка/отписка на пользователей

Capacity <br>
Per year = 2кб/с * 86400 * 365 = 63Гб <br>
IOPS = 2330 <br>
Throughput = 49 кб/с

HDD <br>
IOPS (24) <br>
Throughput (24) <br>
Capacity (1) <br>
Кол-во HDD = 24

SSD (SATA) <br>
IOPS (3) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во SSD (SATA) = 3

SSD (nVME) <br>
IOPS (1) <br>
Throughput (1) <br>
Capacity (1) <br>
Кол-во SSD (nVME) = 1

Используем диски SSD (SATA) = 3 <br>


- Реакции

Шардирование по post_id

Репликация:
1 мастер + 1 синхронная реплика + 1 асинхронная реплика

Кол-во дисков SSD (SATA) = 60 

1 хост это 2 диска <br>
Для репликации потребуется 90 хостов (30+30+30)

- Комментарии

Шардирование по post_id

Репликация:
1 мастер + 1 синхронная реплика + 1 асинхронная реплика

Кол-во SSD (SATA) = 233 

1 хост это 2 диска <br>
Для репликации потребуется 351 хостов (117*3)

- Посты

Шардирование по месяцам даты публикации

Репликация:
1 мастер + 1 синхронная реплика + 1 асинхронная реплика

Кол-во SSD (SATA) = 24

1 хост это 2 диска <br>
Для репликации потребуется 36 хостов (12*3)

- Медиаданные

CDN - 1 мастер + 2 геораспределенных сервера

Кол-во SSD (SATA) = 24

1 хост это 2 диска <br>
Для репликации потребуется 36 хостов (12*3)

- Подписка/отписка на пользователей

Шардирование по user_id

Репликация:
1 мастер + 1 синхронная реплика + 1 асинхронная реплика

Кол-во SSD (SATA) = 3

1 хост это 2 диска <br>
Для репликации потребуется 6 хостов (2*3)
