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

Используем диски SSD (nVME) = 6 (большое кол-во из-за IOPS) <br>

- Комментарии

Capacity <br>
Per year = 116кб/с * 86400 * 365 = 3.7Тб <br>
IOPS = 232638 <br>

Считаем IOPS <br>
RPS (read) = 10_000_000 * 2000 (200 постов в день * 10 комментариев у каждого) / 86400 = 231481 <br /> 
RPS (write) = 10_000_000 * 10 / 86400 = 1157  <br />
Итого = 231481 + 1157 = 232638

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

Используем диски SSD (nVME) = 24 (большое кол-во из-за IOPS) <br>

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


Шардирование и репликация

- Реакции

Шардирование по post_id

Репликация:
1 мастер + 1 синхронная реплика + 1 асинхронная реплика

Кол-во дисков SSD (nVME) = 6

1 хост это 2 диска <br>
Shards = 6/2 = 3 <br>
Для репликации потребуется 3 * 3 = 9 хостов (RF=3)

- Комментарии

Шардирование по post_id

Репликация:
1 мастер + 1 синхронная реплика + 1 асинхронная реплика

Кол-во SSD (nVME) = 24

1 хост это 2 диска <br>
Shards = 24/2 = 12 <br>
Для репликации потребуется 3*12 = 36 хостов  (RF=3)

- Посты

Шардирование по user_id

Репликация:
1 мастер + 1 синхронная реплика + 1 асинхронная реплика

Кол-во SSD (SATA) = 24

1 хост это 2 диска <br>
Shards = 24/2 = 12 <br>
Для репликации потребуется 36 хостов (12*3)

- Подписка/отписка на пользователей

Шардирование по user_id

Репликация:
1 мастер + 1 синхронная реплика + 1 асинхронная реплика

Кол-во SSD (SATA) = 3

1 хост это 2 диска <br>
Shards = 3/2 = 2 <br>
Для репликации потребуется 6 хостов (2*3)
