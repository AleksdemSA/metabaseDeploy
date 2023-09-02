# Metabase Deploy in Kubernetes


Необходимо добавить коллекцию Ansible для Kubernetes, если раньше этого не было сделано
```sh
ansible-galaxy collection install kubernetes.core
```


Теперь можно заменить настройки в roles/metabase/defaults/main.yml и запустить развёртывание
```sh
ansible-playbook role/metabase/application.yml
```

Или можно указать некоторые переменные в момент развёртывания. Разумеется, можно вынести все необходимые переменные в строку запуска по аналогии с уже указанными. Например, переменные с паролями, именем нового тестируемого образа и так далее.
```sh
ansible-playbook roles/metabase/application.yml --extra-vars "NAMESPACE=metabasestage DOMAIN=metabase.example.com"
```

