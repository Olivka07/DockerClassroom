![image](https://github.com/user-attachments/assets/19ea4cbc-203b-4a3d-af3d-07ba9fbda981)![image](https://github.com/user-attachments/assets/40c41399-d51c-4bcf-897f-f1e628b4f86c)![image](https://github.com/user-attachments/assets/41afd1dc-f324-444d-b21d-a997b35fd998)![image](https://github.com/user-attachments/assets/bb7610ad-0f2a-400f-8d7a-b1a729a4324c)# DockerClassroom

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











 

































































































