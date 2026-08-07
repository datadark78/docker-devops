# 🐳 Docker Compose: Multi-container DevOps Stack

**Sistema profesional de containerización con Nginx, MySQL y Redis orquestados con Docker Compose.**

![Docker](https://img.shields.io/badge/Docker-Compose-2496ED)
![Services](https://img.shields.io/badge/services-3-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)

---

## 🎯 Servicios

| Servicio | Imagen | Puerto | Propósito |
|----------|--------|--------|-----------|
| **web** | nginx:latest | 8001 | Servidor web |
| **db** | mysql:8.0 | 3306 | Base de datos |
| **cache** | redis:7-alpine | 6379 | Cache distribuido |

---

## 🚀 Inicio rápido

### Levantar stack completo
```bash
docker compose up -d
```

### Ver servicios corriendo
```bash
docker compose ps
```

### Acceder a Nginx
```bash
curl http://localhost:8001
```

### Conectar a MySQL
```bash
docker compose exec db mysql -u root -pdevops123 -e "SHOW DATABASES;"
```

### Detener todo
```bash
docker compose down
```

### Limpiar volúmenes (CUIDADO - borra datos)
```bash
docker compose down -v
```

---

## 📁 Estructura

docker-devops/
├── docker-compose.yml # Orquestación de servicios
├── Dockerfile # Imagen personalizada de Nginx
├── index.html # Página web personalizada
└── README.md # Este archivo


---

## 🔧 Configuración

### Docker Compose (`docker-compose.yml`)

```yaml
services:
  web:
    image: nginx:latest
    ports: 8001:80
    networks: devops-network
    
  db:
    image: mysql:8.0
    environment:
      MYSQL_ROOT_PASSWORD: devops123
      MYSQL_DATABASE: devops_db
    volumes: mysql-data:/var/lib/mysql
    
  cache:
    image: redis:7-alpine
    ports: 6379:6379
```

### Variables de entorno MySQL

MYSQL_ROOT_PASSWORD: devops123
MYSQL_DATABASE: devops_db


---

## 📊 Casos de uso

✅ Desarrollo local de aplicaciones multi-tier  
✅ Testeo de arquitecturas  
✅ Prototipado rápido  
✅ Ambiente similar a producción  
✅ Aprendizaje de containerización  

---

## 🔒 Seguridad

- ✅ Red privada entre servicios (devops-network)
- ✅ Volúmenes persistentes para datos
- ✅ Containers aislados
- ⚠️ Usar contraseñas reales en producción

---

## 📈 Próximos pasos

- [ ] Desplegar en AWS ECS
- [ ] Agregar Kubernetes manifests
- [ ] Implementar GitHub Actions CI/CD
- [ ] Agregar Prometheus + Grafana

---

## 📚 Recursos

- [Docker Documentation](https://docs.docker.com/)
- [Docker Compose Reference](https://docs.docker.com/compose/compose-file/)
- [MySQL Docker Image](https://hub.docker.com/_/mysql)
- [Redis Docker Image](https://hub.docker.com/_/redis)

---

## 📄 Licencia

MIT - Libre para usar y modificar

---

**Última actualización:** Julio 24, 2026
# CI/CD test
# CI/CD test
