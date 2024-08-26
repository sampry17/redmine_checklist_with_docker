# Redmine с Docker и плагином Checklist

## Предварительные требования

- Docker
- Docker Compose
- Git

## Шаги

### 1. Клонирование репозитория

```bash
git clone https://github.com/sampry17/redmine_checklist_with_docker.git
cd redmine_checklist_with_docker
```

### 2. Запуск Docker Compose

```bash
docker-compose up -d
```

### 3. Клонирование плагина Checklists

```bash
sudo git clone https://github.com/sampry17/redmine_checklists.git storage/docker_redmine-plugins/redmine_checklists
```

### 4. Перезапуск контейнеров

```bash
docker-compose up -d
```

### 5. Вход в контейнер Redmine

```bash
docker exec -it redmine_checklist_with_docker_redmine_1 bash
```

### 6. Применение миграций плагина

```bash
cd /usr/src/redmine
bundle exec rake redmine:plugins:migrate NAME=redmine_checklists RAILS_ENV=production
```

### 7. Перезапуск контейнеров

```bash
docker-compose up -d
```

### Доступ к Redmine 

```bash
http://localhost:8080
```
