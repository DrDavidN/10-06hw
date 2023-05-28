# 10-06hw
# «Disaster recovery» - Дрибноход Давид

## Задание 1.

BaaS - управляемый корпоративный облачный сервис резервного копирования. Основная цель инструмента – скорейшее  восстановление файлов, папок и целых хранилищ данных при полной или частичной потере. Сервис предназначен для  долгосрочной перспективы. Поэтому восстановление больших объемов данных занимает некоторое время.

Облачные предложения DRaaS разработаны с целью быстрой регенерации инфраструктуры посредством высокой скорости  аварийного восстановления и минимизации потери данных. DRaaS создает виртуальную копию операционной системы или ВМ с  незамедлительным доступом по запросу.

Кластер "Active-Active" обычно состоит как минимум из двух узлов, на каждом из которых одновременно запущены  службы одного типа. Основная цель такого кластера — добиться балансировки нагрузки. Балансировка нагрузки распределяет  рабочие нагрузки по всем узлам, чтобы предотвратить перегрузку любого отдельного узла. Поскольку для обслуживания  доступно больше узлов, также будет заметно улучшение пропускной способности и времени отклика.

Подобно конфигурации кластера "Active-Active", кластер "Active-Passive" также состоит как минимум из двух узлов.  Однако, как следует из названия "Active-Passive", не все узлы будут активными. В случае двух узлов, например,  если первый узел уже активен, второй узел должен быть пассивным или находиться в режиме ожидания.

Пассивный сервер служит в качестве резервного узла, готового взять на себя обработку запросов, как только активный  (основной) сервер отключается или не может обслуживать сервис.

Ключевое различие между этими двумя архитектурами заключается в производительности. Кластеры "Active-Active"  обеспечивают доступ к ресурсам на постоянном уровне производительности, заложенными в алгоритме балансировщика нагрузки.  Например, при отказе одного узла, клиент не заметит просадок производительности сервиса. А в кластере  "Active-Passive", может потребоваться некоторое время для включения в работу резервного сервера.

## Задание 2.

План резервного копирования: 
1. Диск /dev/sda1 DRaas в 7:00 и 19:00 - первый полный backup последующие 5 инкрементных 
2. Диск /dev/sda4 BaaS в 7:00 и 19:00 - первый полный backup последующие 5 инкрементных

Чтобы выбрать подходящую модель аварийного восстановления нужно: 
1. Посчитать, какие убытки понесет бизнес в результате простоя. 
2. Подобрать такие RTO и RPO, когда вероятные потери перевешивают затраты на организацию Disaster Recovery. 
То есть найти баланс между расходами на катастрофоустойчивость и убытками компании в случае катастрофы с учетом времени восстановления бизнес-процессов и объема потери данных.

