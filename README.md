![image](https://github.com/user-attachments/assets/bb7610ad-0f2a-400f-8d7a-b1a729a4324c)# DockerClassroom

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
     - 











































