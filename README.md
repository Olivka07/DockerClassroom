# DockerClassroom

## Getting Started Walk-through for IT Pros and System Administrators
- The Basics.
  1) Your First Linux Containers.
     - Запуск контейнера на основе образа hello-world с помощью команды: '''docker container run hello-world''' ![image](https://github.com/user-attachments/assets/527f5910-20f3-4917-97d8-3d970cd25865)
     - Извлечение образа Alpine из реестра DockerHub : ```docker image pull alpine``` ![image](https://github.com/user-attachments/assets/8c2e6f42-1138-4c8b-8bfd-82de57195610)
     - Просмотр всех образов в системе: ```docker image ls``` ![image](https://github.com/user-attachments/assets/22389c84-8525-46d6-84d3-49b9d42c3a8a)
     - Запуск контейнера на основе Apline с командой внутри контейнера для отображения директорий: ```docker container run alpine ls -l``` ![image](https://github.com/user-attachments/assets/c015f097-33dd-4182-aa59-91228a252d19)
     - Запуск и вывод на экран сообщения: ```docker container run alpine echo "hello from alpine"``` ![image](https://github.com/user-attachments/assets/df06ca7b-46f6-4daa-afa3-ad29a8cd9bc6)
     - Запуск sh: ```docker container run alpine /bin/sh``` ![image](https://github.com/user-attachments/assets/614e41cb-cbb7-404b-920f-08f54bb4776c)
     - Запуск sh в интерактивном режиме: ```docker container run -it alpine /bin/sh``` ![image](https://github.com/user-attachments/assets/e25dce4a-3554-4df5-b8d4-ab78e51d86b2)
     - Отображение всех запущенных контейнеров: ```docker container ls``` ![image](https://github.com/user-attachments/assets/71575936-6be5-4e5f-b087-c37cfdc0f7dd)
     - Отображение всех контейнеров: ```docker container ls -a``` ![image](https://github.com/user-attachments/assets/88899b1e-8415-43b5-9441-b660e865e4f9)
     - Запуск ash в интерактивном режиме: ```docker container run -it alpine /bin/ash``` ![image](https://github.com/user-attachments/assets/57405927-0e32-47b7-af6f-3cb973cc859a)
     - Создание hello.txt файла и добавление в него контента в контейнере, отображение содержимого текущей директории: ```echo "hello world" > hello.txt && ls``` ![image](https://github.com/user-attachments/assets/bcd2b9e0-8123-47f8-b456-3939af5d7ab1)
     - Запуск нового контейнера и отображение там содержимого директории для того, чтобы убедиться, что они изолированные: ```docker container run alpine ls``` ![image](https://github.com/user-attachments/assets/8f8cc0d7-3659-4abc-95c6-482750a3668b)
     - Отображение всех контейнеров: ```docker container ls -a``` ![image](https://github.com/user-attachments/assets/36caa2e3-daa1-4c32-bec9-c8208d8030c2)
     - Запуск контейнера, в котором был создан файл hello.txt: ```docker container start fcb``` ![image](https://github.com/user-attachments/assets/437a1c3d-cec0-45f6-881e-0dcf7b53c09e)
     - Просмотр всех запущенных контейнеров: ```docker container ls``` ![image](https://github.com/user-attachments/assets/6911bbf4-68c5-4821-8cfd-b732b712ce8e)
     - Отправка команды для отображения содержимого директории контейнеру: ```docker container exec <container ID> ls``` ![image](https://github.com/user-attachments/assets/434d5efa-987f-456d-87e8-1ccfc6540c5b)
  2) Customizing Docker Images.
     - Запуск интерактивной оболочки в контейнере ubuntu: ```docker container run -ti ubuntu bash``` ![image](https://github.com/user-attachments/assets/5ce93417-9d92-47f0-b47b-aac111ae0acd)
     - Установка пакета figlet в контейнере: ```apt-get update
                                              apt-get install -y figlet
                                              figlet "hello docker"
                                             ``` ![image](https://github.com/user-attachments/assets/8f3ce0d1-060f-4901-9902-4001838d743d)
     - Получение идентификатора контейнера через список всех контейнеров: ```docker container ls -a``` ![image](https://github.com/user-attachments/assets/5a428641-a257-4690-9158-2bca74276071)
     - Команда для просмотра внесенных изменений: ```docker container diff 1bbb``` ![image](https://github.com/user-attachments/assets/7a2df273-7dee-4e23-b694-ed7691d5e42f)
     - Фиксация контейнера для создания образа: ```docker container commit 1bbb``` ![image](https://github.com/user-attachments/assets/0ee34c4f-6ad8-4f42-b81f-fa4c6633f22f)
     - Просмотр списка образов с созданным только что образом: ```docker image ls```![image](https://github.com/user-attachments/assets/44ce3435-4fac-45bc-9abb-c2da6594fae4)
     - Тегирование новосозданного образа: ```docker image tag f129dc ourfiglet && docker image ls``` ![image](https://github.com/user-attachments/assets/e3e03655-3ff2-4601-8e3b-ec2cee945499)
     - Запуск контейнера на основе новосозданного образа: ```docker container run ourfiglet figlet hello``` ![image](https://github.com/user-attachments/assets/48c11fcc-6dae-4a86-9fd3-bf995f458234)
     - Создание Dockerfile для образа с NodeJS: ![image](https://github.com/user-attachments/assets/7482ddc6-0658-4d7f-8eb3-bc4257732178)
     - Создание образа на основе Dockerfile: ```docker image build -t hello:v0.1 .``` ![image](https://github.com/user-attachments/assets/d919f650-ebd5-44e6-8677-0849c3dbde93)
     - Запуск контейнера: ```docker container run hello:v0.1``` ![image](https://github.com/user-attachments/assets/062cf9a5-263a-4fe5-994c-8961d1ab8a20)
     - Просмотреть список промежуточных образов: ```image history 070c``` ![image](https://github.com/user-attachments/assets/7900b7ce-60d9-4d70-95d9-05d840a83ed0)
     - Создание образа с помощью Dockerfile после внесения изменений: ```docker image build -t hello:v0.2 .``` ![image](https://github.com/user-attachments/assets/2f2b4de2-09d1-49f3-ac76-908b871869d5)
     - Просмотр информации об образе alpine: ```docker image inspect alpine``` ![image](https://github.com/user-attachments/assets/9ebbb309-1685-4f3a-b78e-4f7fa77e9997)
     - Получение списка слоев отфильтровав предыдущую информацию: ```docker image inspect --format "{{ json .RootFS.Layers }}" alpine``` ![image](https://github.com/user-attachments/assets/9f35ddca-552c-4b85-a707-6836ddb896a8)
     - Получение списка слоев образа hello: ```docker image inspect --format "{{ json .RootFS.Layers }}" 103a``` ![image](https://github.com/user-attachments/assets/acf20c3c-1813-4989-9dad-71872cdab361)
  3) Deploy and Managing Multiple Containers.
     - Инициализация Docker Swarm Mode в первом терминале: ```docker swarm init --advertise-addr $(hostname -i)``` ![image](https://github.com/user-attachments/assets/f53e3d9f-4435-44b0-a76d-0bd65893996b)
     - Добавление рабочего узла во втором терминале: ```docker swarm join --token SWMTKN-1-22oxrwampkqolj9ze18gnr6z3nwvxw7ea1wzy04evvq2wt9h3p-a52621btg2z5lwuwogel3h42i 192.168.0.18:2377``` ![image](https://github.com/user-attachments/assets/111667df-d80e-43ed-a991-955e8d516911)
     - Проверка количкства узло Swarm: ```docker node ls``` ![image](https://github.com/user-attachments/assets/3ee4cd86-2455-423c-bf84-69a09feb6b6f)
     - Клонирование репозитория с приложением для голосования и переход в рабочую директорию в первом терминале: ```git clone https://github.com/docker/example-voting-app``` ![image](https://github.com/user-attachments/assets/81cbf1b4-bc09-4b5c-a5cc-62c651737c64)
     - Посмотреть содержимое файла конфигурации Stack - группы служб: ```cat docker-stack.yml``` ![image](https://github.com/user-attachments/assets/b30b4fe0-ddff-4c0e-bdff-2d12ce87812b)
     - Разворачивание стека приложения для голосвания: ```docker stack deploy --compose-file=docker-stack.yml voting_stack``` ![image](https://github.com/user-attachments/assets/c2d718bf-fc63-4867-98b4-5bfd079f9521)
     - Просмотр запущенных сервисов: ```docker stack ls``` ![image](https://github.com/user-attachments/assets/2421feae-b5f2-4416-ba40-fb7e91053846)
     - Просмотр детальной информации о каждом сервисе: ```docker stack services voting_stack``` ![image](https://github.com/user-attachments/assets/e84168c3-4436-4ec5-ba12-4d2f00616430)
     - Просмотр сервисов службы для голосования: ```docker service ps voting_stack_vote``` ![image](https://github.com/user-attachments/assets/7bb01ce1-c08d-4f5d-b42e-11dba52f6c9f)
     - Масштабирование количества служб до 5: ```docker service scale voting_stack_vote=5``` ![image](https://github.com/user-attachments/assets/3a8b84ba-cd2d-4a76-88e4-38ddc5eedec7)
     - Просмотр сервисов службы для голосвания: ```docker stack services voting_stack``` ![image](https://github.com/user-attachments/assets/311b385a-5108-4de7-a56a-1cfaedac7a58)
- Digging Deeper.
  1) Seccomp profiles.
     - Команда, показывающая включен ли seccomp: ```docker info | grep seccomp``` ![image](https://github.com/user-attachments/assets/5fd841a8-8549-4be0-93d8-606d83c39b6d)
     - Клонирование репозитория с профилями seccomp: ```git clone https://github.com/docker/labs``` ![image](https://github.com/user-attachments/assets/5bca8dd8-95e3-4a80-906a-be3916c7fe40)
     - Запуск контейнера без apparmor и примененным профилем seccomp: ```docker run --rm -it --cap-add ALL --security-opt apparmor=unconfined --security-opt seccomp=seccomp-profiles/deny.json alpine sh``` ![image](https://github.com/user-attachments/assets/c235a697-ea1b-4c41-9cf6-5d1690128040)
     - Проверка содержимого применяемого профиля: ```cat seccomp-profiles/deny.json``` ![image](https://github.com/user-attachments/assets/1e6e384f-bc0b-400a-87e2-8caa561dacc7)
     - Запуск контейнера без профиля seccomp: ```docker run --rm -it --security-opt seccomp=unconfined debian:jessie sh``` ![image](https://github.com/user-attachments/assets/e8d8d1fa-b2b8-42c6-b4e6-3f1cd267a6f8)
     - Проверка роли пользователя: ```whoami``` ![image](https://github.com/user-attachments/assets/8b48d64f-5454-42c3-b094-e2400dae0ba6)
     - Запуск оболочки в новом пространстве имен: ```unshare --map-root-user --user && whoami``` ![image](https://github.com/user-attachments/assets/05952d3e-9db9-4661-8577-a34c09640b5b)
     - Список системных вызовов: ```apk add --update strace && strace -c -f -S name whoami 2>&1 1>/dev/null | tail -n +3 | head -n -2 | awk '{print $(NF)}'``` ![image](https://github.com/user-attachments/assets/4e13e129-3d4f-4d28-bf19-a81676031ab5)
     - Получение дополнительной информации: ```strace whoami``` ![image](https://github.com/user-attachments/assets/6ae7292f-e42b-4656-81f7-1f2c4b14e90d)
     - Запуск контейнера с другим seccomp профилем: ```docker run --rm -it --security-opt seccomp=./seccomp-profiles/default-no-chmod.json alpine sh```
     - Запуск в контейнере команды: ```chmod 777 / -v``` ![image](https://github.com/user-attachments/assets/93534e3c-88aa-47b8-9d9f-81b343c3115f)
     - Запуск контейнера с другим seccomp профилем: ```docker run --rm -it --security-opt seccomp=./seccomp-profiles/default.json alpine sh```
     - Запуск в контейнере команды: ```chmod 777 / -v``` ![image](https://github.com/user-attachments/assets/401a64bb-a5c9-4dd6-bda2-5c5a4a82067b)
     - Проверка доступных системных вызовов: ```cat ./seccomp-profiles/default.json | grep chmod``` ![image](https://github.com/user-attachments/assets/7a0534fa-5ab6-4d2c-98b9-78863ab40bf0)
     - Проверка доступных системных вызовов другого профиля: ```cat ./seccomp-profiles/default-no-chmod.json | grep chmod``` ![image](https://github.com/user-attachments/assets/c6de82d9-e8cc-450f-bb18-ab200f45a4d8)
     - Получения списка всех системных вызовов: ```strace -c -f -S name ls 2>&1 1>/dev/null | tail -n +3 | head -n -2 | awk '{print $(NF)}'``` ![image](https://github.com/user-attachments/assets/9c16fe81-bfdb-4ab1-b43a-0ca6121ed218)
  2) Linux Kernel Capabilities and Docker.
     - Создание контейнера и изменение владельца файла: ``` docker run --rm -it alpine chown nobody /``` ![image](https://github.com/user-attachments/assets/0b21761e-42cd-4509-bba7-895f3920813b)
     - Запуск другого контейнера и удаление всех возможностей root кроме CHOWN: ``` docker run --rm -it --cap-drop ALL --cap-add CHOWN alpine chown nobody /``` ![image](https://github.com/user-attachments/assets/f4ecbaa5-feaf-4d9b-b407-6db305443138)
     - Запуск другого контейнера и удаление только CHOWN: ``` docker run --rm -it --cap-drop CHOWN alpine chown nobody /``` ![image](https://github.com/user-attachments/assets/05991512-4ec4-4daf-9896-d6c8f2bb4afd)
     - Запуск контейнера и добавление chown пользователю nobody: ```docker run --rm -it --cap-add chown -u nobody alpine chown nobody /``` ![image](https://github.com/user-attachments/assets/7ce850a7-1c66-4756-86f2-df3eb95307f7)
     - Запуск контейнера, установка libcap и вывод списка всех возможностей: ```docker run --rm -it alpine sh -c 'apk add -U libcap; capsh --print'``` ![image](https://github.com/user-attachments/assets/0310f9c9-b7ea-4fbf-8cfd-2eeacf2873fe)
     - Вывод всех доступных команд: ```docker run --rm -it alpine sh -c 'apk add -U libcap;capsh --help'``` ![image](https://github.com/user-attachments/assets/806a1143-e62e-4f78-8103-665d1c8fae9e)
  3) Docker Networking Hands-on Lab.
     - Настройка и управление сетями контейнеров: ```docker network``` ![image](https://github.com/user-attachments/assets/2765681f-51d0-4d90-9b27-1c47e8015b36)
     - Вывод листа сетей: ```docker network ls``` ![image](https://github.com/user-attachments/assets/1c82757d-162e-4c59-a7cb-658a8e3cc60e)
     - Получение информации о сети: ```docker network inspect bridge``` ![image](https://github.com/user-attachments/assets/d4279beb-7c09-4ff8-a095-6762ce167010)
     - Получение об установленном Docker информации: ```docker info``` ![image](https://github.com/user-attachments/assets/cb05fb8f-4ced-42af-ae5a-ae2d0a2ee9ff)
     - Установка пакета brctl: ```apk update && apk add bridge``` ![image](https://github.com/user-attachments/assets/f962ea92-ae9d-4de5-b729-75b2e234c34b)
     - Вывод списка мостов хостовой машины: ```brctl show``` ![image](https://github.com/user-attachments/assets/72989320-814b-4e5d-8a41-a41ae29555ec)
     - Команда для просмотра деталей о docker0 мосте: ```ip a``` ![image](https://github.com/user-attachments/assets/b0a36a21-c392-48a5-83e5-9065fa10dd0d)
     - Запуск контейнера в спящем режиме: ```docker run -dt ubuntu sleep infinity``` ![image](https://github.com/user-attachments/assets/73b7f13d-c15f-4382-bc0c-4b32ba3939c7)
     - Вывод списка мостов: ```brctl show``` ![image](https://github.com/user-attachments/assets/ddef3f09-58aa-4b84-afef-94be6a4988a2)
     - Вывод деталей о сети снова: ```docker network inspect bridge``` ![image](https://github.com/user-attachments/assets/b3c15da0-1ae1-4a14-a54f-68da0226f3f1)
     - Запуск контейнера и оболочки sh внутри: ```docker exec -it 1396 /bin/bash``` ![image](https://github.com/user-attachments/assets/1a484224-bf1b-464e-a2a2-3d3951bd7187)
     - Установка необходимых пакетов внутри контейнера: ```apt-get update && apt-get install -y iputils-ping``` ![image](https://github.com/user-attachments/assets/16affeb2-d8e9-4399-895d-97f4a09c0609)
     - Пингуем GitHib: ```ping -c5 www.github.com``` ![image](https://github.com/user-attachments/assets/f0f2198a-72b9-45fb-915d-0c2e3b9ea052)
     - Запуск образа nginx: ```docker run --name web1 -d -p 8080:80 nginx``` ![image](https://github.com/user-attachments/assets/10bfb154-7ae8-4383-867d-f892d1a22801)
     - Обратиться на хостовой машине к порту 8080: ```curl 127.0.0.1:8080``` ![image](https://github.com/user-attachments/assets/d856c266-9145-4b71-bbc8-ded914eb6fdf)
     - Проинициализировать Swarm Mode: ```docker swarm init --advertise-addr $(hostname -i)``` ![image](https://github.com/user-attachments/assets/1aeae33a-44fc-4e97-a5d4-4de06987c13c)
     - Во втором терминале стать работником: ```docker swarm join --token SWMTKN-1-58dvaeja6s7zedav1mm2ed0dts2dpp6gp0l66ps1ig25qnf42k-ag2r4fc30gj0svsar9gwkz5mz 192.168.0.17:2377``` ![image](https://github.com/user-attachments/assets/89ba9ef9-cae6-4f0b-8533-5115ec99b585)
     - Проверка всех узлов Swarm: ```docker node ls``` ![image](https://github.com/user-attachments/assets/ca1b2e9e-02a7-43e3-a8b4-27b37587be89)
     - Создание сети: ```docker network create -d overlay overnet``` ![image](https://github.com/user-attachments/assets/f1841284-63ea-431e-a862-fc3bc7f5a48b)
     - Вывод списка сетей: ```docker network ls``` ![image](https://github.com/user-attachments/assets/c996b95e-5e96-46a3-8f2c-8e6eedaccd4f)
     - Вывод списка сетей из второго терминала: ```docker network ls``` ![image](https://github.com/user-attachments/assets/fb59704e-3c2c-4451-9b5f-d4edd4e21aaf)
     - Получить детали о сети: ```docker network inspect overnet``` ![image](https://github.com/user-attachments/assets/bbc1bb83-2d5a-4e7d-9c46-0ee8cbbcdda3)
     - Создание службы использующую эту сеть: ```docker service create --name myservice \
                                              --network overnet \
                                              --replicas 2 \
                                              ubuntu sleep infinity``` ![image](https://github.com/user-attachments/assets/8e9fb98f-dde2-40b0-b9b1-9dbb06adc02e)
     - Получение списка запущенных сервисов: ```docker service ls``` ![image](https://github.com/user-attachments/assets/0a9c6570-e8e3-484e-820b-f730803eb0ee)
     - Получение списка реплик сервиса: ```docker service ps myservice``` ![image](https://github.com/user-attachments/assets/cdd449ac-d07a-4ba5-b90a-512518bb5cee)
     - Проверка сетей теперь во втором терминале: ```docker network ls``` ![image](https://github.com/user-attachments/assets/4b1ccfed-7913-4ddb-874a-81751a65a8c4)
     - Получить детали сети во втором терминале: ```docker network inspect overnet``` ![image](https://github.com/user-attachments/assets/0f9ef377-ee43-450f-967b-ec30ce05e5b9)
     - Получить детали сети в первом терминале: ```docker network inspect overnet``` ![image](https://github.com/user-attachments/assets/9995f667-8a42-40b9-9dcd-a853f5904704)
     - Установка необходимых зависимостей приводит к ошибке: ```apt-get update && apt-get install -y iputils-ping``` ![image](https://github.com/user-attachments/assets/b8bea1f2-da98-43e3-901f-21539c8fa227)
     - Получение содержимого внутри resolve.conf: ```cat /etc/resolv.conf``` ![image](https://github.com/user-attachments/assets/d49a1307-9051-443b-89c8-1ee85f7b676f)
     - Удаление сервиса: ```docker service rm myservice``` ![image](https://github.com/user-attachments/assets/0d8be820-f067-4f03-9503-09cb9d6122ec)
     - Убийство контейнера: ```docker kill 777``` ![image](https://github.com/user-attachments/assets/a3ceb571-8e69-4f67-abb4-d5210a4e8560)
     - Подкидание swarm: ```docker swarm leave --force``` ![image](https://github.com/user-attachments/assets/b995aa6a-8be9-4eeb-96ee-7a45b6101c45)
  4) Docker Orchestration Hands-on Lab.
     - ```docker run -dt ubuntu sleep infinity``` ![image](https://github.com/user-attachments/assets/d4c7ea25-61f5-47f4-a32e-b8aed0548a74)
     - ```docker swarm init --advertise-addr $(hostname -i)``` ![image](https://github.com/user-attachments/assets/43e941aa-8bde-48b3-ba12-dbd422ebe710)
     - ```docker swarm join --token SWMTKN-1-1bvr921hp40vnyfqijo4tainalmvxsk761n6g914jnnm359s4p-6wuyt0oyd2lf4wsw6llkriao0 192.168.0.28:2377``` ![image](https://github.com/user-attachments/assets/a44ea384-a84f-4b08-a4a5-498946d48111)
     - ```docker node ls``` ![image](https://github.com/user-attachments/assets/d110eab6-d6dd-42d7-9559-090136b61190)
     - ```docker service create --name sleep-app ubuntu sleep infinity``` ![image](https://github.com/user-attachments/assets/e55fd81f-f473-4345-adb9-2d80c6c76c62)
     - ```docker service update --replicas 7 sleep-app``` ![image](https://github.com/user-attachments/assets/8d56f1e5-6497-4b79-898f-bb823cd76608)
     - ```docker service ps sleep-app``` ![image](https://github.com/user-attachments/assets/7059f3d5-e84b-466c-98f8-f7b23d19f5a3)
     - ```docker service update --replicas 4 sleep-app``` ![image](https://github.com/user-attachments/assets/278aa9ca-1c7e-4c87-a104-5e7748e44f5b)
     - ```docker node ls``` ![image](https://github.com/user-attachments/assets/78a85295-7c8c-4797-8f1a-4bcb78e8961f)
     - ```docker node update --availability drain ra88``` ![image](https://github.com/user-attachments/assets/99c36397-4b9d-4bed-8555-28042d179b7e)
     - ```docker node ls``` ![image](https://github.com/user-attachments/assets/58dcc089-706f-4c45-95a1-546fba276753)
     - ```docker service ps sleep-app``` ![image](https://github.com/user-attachments/assets/706d0805-96b4-4605-a20f-3a83072ad6c5)
     - ```docker service rm sleep-app``` ![image](https://github.com/user-attachments/assets/291e0144-cae4-4aac-a932-9f931dd61cfc)
     - ```docker swarm leave --force``` ![image](https://github.com/user-attachments/assets/28c00db9-7fce-4063-a768-0588b38fa68e)

## Getting Started Walk-through for Developers
- The Basics.
  1) Docker for Beginners - Linux.
     - Клонирование репозитория: ```git clone https://github.com/dockersamples/linux_tweet_app``` ![image](https://github.com/user-attachments/assets/d951213c-6a41-458e-af3b-945920f0cf96)
     - Запуск контейнера на основе образа alpine с командой hostname: ```docker container run alpine hostname``` ![image](https://github.com/user-attachments/assets/a320758a-5e9d-4faa-b6f6-15263e4c7a50)
     - Все контейнеры: ``` docker container ls --all``` ![image](https://github.com/user-attachments/assets/366bf106-8e6c-4009-871e-721078f1ccfb)
     - ``` docker container run --interactive --tty --rm ubuntu bash``` ![image](https://github.com/user-attachments/assets/5a1a6df1-2960-4053-b759-25d1651647df)
     - ```ls /``` ![image](https://github.com/user-attachments/assets/e37ea4f8-00f6-438b-a499-29b85b268186)
     - Запущенные процессы: ```ps aux``` ![image](https://github.com/user-attachments/assets/d9043d02-3875-44ea-8d19-74c047eb0251)
     - Версия дистрибутива Linux: ```cat /etc/issue``` ![image](https://github.com/user-attachments/assets/62879d42-014c-4e98-9785-d3d9e175a6de)
     - ``` cat /etc/issue``` ![image](https://github.com/user-attachments/assets/fe2f6d78-702a-4dd3-8856-7473c6c4a2ff)
     - Запуск контейнера на основе образа mysql: ``` docker container run \
                                                   --detach \
                                                   --name mydb \
                                                   -e MYSQL_ROOT_PASSWORD=my-secret-pw \
                                                   mysql:latest
                                                 ``` ![image](https://github.com/user-attachments/assets/f50d1e8d-b636-455c-8595-316a689083d2)
     - ``` docker container ls``` ![image](https://github.com/user-attachments/assets/d26ecbc2-e6b1-4704-847b-5cf11f11fe5f)
     - ```docker container logs mydb``` ![image](https://github.com/user-attachments/assets/bad7d95f-a2c3-4fea-bdda-608abce55c38)
     - Процессы запущенные внутри контейнера: ```docker container top mydb``` ![image](https://github.com/user-attachments/assets/e1b3e65d-3bee-46f6-99f0-70762e2bcd5e)
     - ```docker exec -it mydb mysql --user=root --password=$MYSQL_ROOT_PASSWORD --version``` ![image](https://github.com/user-attachments/assets/9c0d582b-514a-45a6-8aef-331c43d12ab1)
     - ```docker exec -it mydb sh``` ![image](https://github.com/user-attachments/assets/c730c660-45f2-47ab-8bec-63abe3f8f77c)
     - ``` mysql --user=root --password=$MYSQL_ROOT_PASSWORD --version``` ![image](https://github.com/user-attachments/assets/1a6c0943-1887-41e5-8d20-55188a41ad6e)
     - ``` cd ~/linux_tweet_app``` ![image](https://github.com/user-attachments/assets/6fb47857-d332-4b57-8e21-8b5926ac101b)
     - ```cat Dockerfile``` ![image](https://github.com/user-attachments/assets/da49b8fc-e124-48da-8a6c-533d9718e652)
     - ```export DOCKERID=olivka07```![image](https://github.com/user-attachments/assets/972ceb50-0b80-499b-96e6-2cf09d8b794e)
     - ```echo $DOCKERID``` ![image](https://github.com/user-attachments/assets/c15e7a06-342a-4873-9dbb-c52ab39df97f)
     - ```docker image build --tag $DOCKERID/linux_tweet_app:1.0 .``` ![image](https://github.com/user-attachments/assets/a616b761-b1e3-4d9f-813f-ed38c893a88b)
     - ``` docker container run --detach --publish 80:80 --name linux_tweet_app $DOCKERID/linux_tweet_app:1.0``` ![image](https://github.com/user-attachments/assets/418f13dc-1021-4367-88d3-194010f823b4)
     - Зайти на сайт: ![image](https://github.com/user-attachments/assets/3ac8c7b4-078d-4389-8593-83af11a26c59)
     - ```docker container rm --force linux_tweet_app``` ![image](https://github.com/user-attachments/assets/255a6e63-fc9d-4b92-a268-81b6217f0f8a)
     - ``` docker container run --detach --publish 80:80 --name linux_tweet_app --mount type=bind,source="$(pwd)",target=/usr/share/nginx/html $DOCKERID/linux_tweet_app:1.0``` ![image](https://github.com/user-attachments/assets/5f9549cc-029c-495a-b5ac-74f52e06edc4)
     - Запущенный веб-сайт: ![image](https://github.com/user-attachments/assets/33dbd69b-3905-4751-ba88-d438c2f2891c)
     - ```cp index-new.html index.html``` ![image](https://github.com/user-attachments/assets/fd446949-dd82-4ff9-b1ad-5d019d204ce3)
     - Запущенный веб-сайт после изменений: ![image](https://github.com/user-attachments/assets/4710b853-ba8c-449a-95ae-fc0b7d527179)
     - ``` docker image build --tag $DOCKERID/linux_tweet_app:2.0 .``` ![image](https://github.com/user-attachments/assets/241436d5-4b7b-48f3-9edd-c6343ea455b3)
     - ```docker image ls``` ![image](https://github.com/user-attachments/assets/ecd9c9ca-a3b9-4040-9b2b-0b016cbce2d6)
     - ```docker container run --detach --publish 80:80 --name linux_tweet_app $DOCKERID/linux_tweet_app:2.0``` ![image](https://github.com/user-attachments/assets/540e6ae4-7547-4323-b99b-32073971e60b)
     - ``` docker container run --detach --publish 8080:80 --name old_linux_tweet_app $DOCKERID/linux_tweet_app:1.0``` ![image](https://github.com/user-attachments/assets/75efc24d-259a-4c9d-ab2c-36ce0ec370e1)
     - ``` docker image ls -f reference="$DOCKERID/*"``` ![image](https://github.com/user-attachments/assets/62c356de-aa0c-4195-845c-ee44d551c722)
     - ``` docker login``` ![image](https://github.com/user-attachments/assets/c0f07a97-925c-4f64-984d-4d20fb332f85)
     - ``` docker image push $DOCKERID/linux_tweet_app:1.0``` ![image](https://github.com/user-attachments/assets/05476bbd-de65-466b-8f4e-a871fc3f26b0)
     - ``` docker image push $DOCKERID/linux_tweet_app:2.0```  ![image](https://github.com/user-attachments/assets/81667e29-c8d8-4c3d-9b6f-3f1b14cd61f8)
     - DockerHub: ![image](https://github.com/user-attachments/assets/2d4898fb-6fd1-4a00-b1d8-213bc9744977)
  2) Application Containerization and Microservice Orchestration.
     - ```git clone https://github.com/ibnesayeed/linkextractor.git && cd linkextractor && git checkout demo``` ![image](https://github.com/user-attachments/assets/74555e93-553d-47e4-93fe-dcf511e0df97)
     - ```git checkout step0 && tree``` ![image](https://github.com/user-attachments/assets/1fad1311-d069-4bdb-ac82-6406321c6d8c)
     - ```cat linkextractor.py``` ![image](https://github.com/user-attachments/assets/5a4dedae-69f0-4e35-a783-c170c72b1686)
     - ```./linkextractor.py http://example.com/``` ![image](https://github.com/user-attachments/assets/95c9f6ec-7ec2-489e-b0be-3e18981dfb79)
     - ```ls -l linkextractor.py``` ![image](https://github.com/user-attachments/assets/7c48d480-fda1-4f77-87e1-530f3f7c2b0f)
     - ```python3 linkextractor.py``` ![image](https://github.com/user-attachments/assets/b407364a-2599-4ed0-a339-65a18fc7ab6d)
     - ```git checkout step1 && tree``` ![image](https://github.com/user-attachments/assets/dd1c45de-fc2d-4639-b667-956715c0fcd1)
     - ```cat Dockerfile``` ![image](https://github.com/user-attachments/assets/6c13196d-effe-4c62-99e0-46f147b3b316)
     - ```docker image build -t linkextractor:step1 .``` ![image](https://github.com/user-attachments/assets/04610472-715b-4427-91cb-685f87e19ee7)
     - ```docker container run -it --rm linkextractor:step1 http://example.com/``` ![image](https://github.com/user-attachments/assets/84380a6d-5cdc-4a7b-8bd8-51082af30beb)
     - ```docker container run -it --rm linkextractor:step1 https://training.play-with-docker.com/``` ![image](https://github.com/user-attachments/assets/6b8ae664-161e-4a39-8504-c4eded95f5a2)
     - ```git checkout step2 && cat linkextractor.py``` ![image](https://github.com/user-attachments/assets/8683330f-aa54-48e9-a66e-308bedc61872)
     - ```docker image build -t linkextractor:step2 .``` ![image](https://github.com/user-attachments/assets/66d2778f-55cf-4e19-9616-3c36c28a6a71)
     - ```docker container run -it --rm linkextractor:step2 https://training.play-with-docker.com/``` ![image](https://github.com/user-attachments/assets/0a2d7745-e71e-476b-bfb2-9a296f767a0e)
     - ```docker container run -it --rm linkextractor:step1 https://training.play-with-docker.com/``` ![image](https://github.com/user-attachments/assets/be3bb3f4-39fb-430c-ba76-d0bfaa920244)
     - ```git checkout step3 && cat Dockerfile``` ![image](https://github.com/user-attachments/assets/3b084ef3-5888-4a5b-ba44-61f7700c8c22)
     - ```cat main.py``` ![image](https://github.com/user-attachments/assets/2528e845-761c-455e-bff1-949004bed864)
     - ```docker image build -t linkextractor:step3 .``` ![image](https://github.com/user-attachments/assets/8d6edccb-a29c-4c48-a3e4-c51f05c0db86)
     - ```docker container run -d -p 5000:5000 --name=linkextractor linkextractor:step3``` ![image](https://github.com/user-attachments/assets/19c89481-4c1c-4b9f-bad5-367ad1fefa42)
     - ```curl -i http://localhost:5000/api/http://example.com/``` ![image](https://github.com/user-attachments/assets/c8d6e1d2-5c68-4602-86a7-f8611067e252)
     - ```docker container logs linkextractor``` ![image](https://github.com/user-attachments/assets/92eaccee-0203-4f24-9502-06ddb1e17f2f)
     - ```git checkout step4 && cat docker-compose.yml``` ![image](https://github.com/user-attachments/assets/dde219dd-1ff5-4b8f-aa26-ba1f6510ae95)
     - ```cat www/index.php``` ![image](https://github.com/user-attachments/assets/7c1d444b-5bd6-480a-ae7a-d69c74e0373a)
     - ```docker-compose up -d --build``` ![image](https://github.com/user-attachments/assets/ef4a4fd6-40f1-4fc1-bcbf-95a637c572ae)
     - ```curl -i http://localhost:5000/api/http://example.com/``` ![image](https://github.com/user-attachments/assets/a4b61cf7-df42-4154-af03-1a41ad846361)
     - ```sed -i 's/Link Extractor/Super Link Extractor/g' www/index.php && git reset --hard && docker-compose down``` ![image](https://github.com/user-attachments/assets/19154b13-9610-4c38-9bef-bd85e7542395)
     - ```git checkout step5 && cat www/Dockerfile && cat api/main.py``` ![image](https://github.com/user-attachments/assets/d24f334d-8b95-409c-a8a7-0d630e6f32c6)
     - ```cat docker-compose.yml``` ![image](https://github.com/user-attachments/assets/efc5d7b3-3ff5-43b6-bdbd-420e3f2696f8)
     - ```docker-compose up -d --build``` ![image](https://github.com/user-attachments/assets/e7f0b155-71ff-4084-b2c5-4e9da78f680b)
     - ```docker-compose exec redis redis-cli monitor``` ![image](https://github.com/user-attachments/assets/b94d2d34-fae7-4eea-8c82-35e3fc760fc3)
     - ```sed -i 's/Link Extractor/Super Link Extractor/g' www/index.php && git reset --hard && docker-compose down```
     - ```git checkout step6 && cat api/linkextractor.rb``` ![image](https://github.com/user-attachments/assets/88190a6b-36b1-450c-95fb-453334aa9e97)
     - ```cat api/Dockerfile && cat docker-compose.yml``` ![image](https://github.com/user-attachments/assets/fd673449-c61b-4a7a-b682-7c8be89ad261)
     - ```docker-compose up -d --build``` ![image](https://github.com/user-attachments/assets/eb87cc6d-df69-42aa-ae58-64167b71b09e)
     - ```curl -i http://localhost:4567/api/http://example.com/``` ![image](https://github.com/user-attachments/assets/e886dfb2-11f0-4b1b-8c95-065255f66bbf)
     - ```docker-compose down``` ![image](https://github.com/user-attachments/assets/67da325d-2784-4d95-9765-1b2dedba1c4d)
     - ```cat logs/extraction.log``` ![image](https://github.com/user-attachments/assets/f13d3bc5-d756-4ed1-aa5e-9e970adde0ff)
  3) Deploying a Multi-Service App in Docker Swarm Mode.
     - ```docker swarm init --advertise-addr $(hostname -i)``` ![image](https://github.com/user-attachments/assets/5eb06725-d754-423b-8fc8-3f44c2b8d645)
     - ```docker node ls``` ![image](https://github.com/user-attachments/assets/8cc08d03-fa8e-4375-83e9-d1aa44504534)
     - ```git clone https://github.com/docker/example-voting-app && cd example-voting-app``` ![image](https://github.com/user-attachments/assets/e788661a-73ba-4a83-895d-831eecf49b19)
     - ```docker stack deploy --compose-file=docker-stack.yml voting_stack``` ![image](https://github.com/user-attachments/assets/26ded4ed-97d3-4299-905e-9e7ead7d3737)
     - ```docker stack ls``` ![image](https://github.com/user-attachments/assets/1dc89253-ed9e-4d4a-9392-18275922e195)
     - ```docker stack services voting_stack``` ![image](https://github.com/user-attachments/assets/0c977c84-b7ee-410c-8e62-ed88b9ec1c19)
     - ```docker service ps voting_stack_vote``` ![image](https://github.com/user-attachments/assets/c2d8427d-b57b-4735-b4a7-afd024544a4a)



















































































 

































































































