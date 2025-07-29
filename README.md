# Proyecto InnovaSys – Automatización con Ansible

Este proyecto forma parte del Desafío de Automatización planteado en el curso de Taller de Sistemas Operativos II. El objetivo es configurar automáticamente un servidor Ubuntu 24.04 desde cero utilizando Ansible, siguiendo buenas prácticas de la industria.

## 📦 Servicios Configurados

### 1. Servidor Web (Apache)
- Instalación del paquete `apache2`
- Despliegue de una página de bienvenida personalizada mediante plantilla Jinja2
- Activación y habilitación del servicio en el arranque
- Uso de variables para contenido dinámico (`nombre_empresa`)

### 2. Servidor de Archivos (Samba)
- Instalación de Samba
- Creación del grupo `desarrolladores` y usuario `devuser1`
- Compartición del directorio `/srv/samba/proyectos`
- Acceso restringido por grupo y protegido por contraseña
- Servicio `smbd` configurado con handler e inicio automático

## ⚙️ Estructura del Proyecto

```
innovaSys/
├── site.yml              # Playbook principal
├── hosts                 # Inventario estático con IP del servidor
├── README.md             # Este archivo
└── roles/
    ├── apache/           # Configura Apache con plantilla Jinja2
    └── samba/            # Configura recurso compartido y usuarios
```

## 🚀 ¿Cómo ejecutar?

1. Asegúrate de estar en la raíz del proyecto.
2. Conéctate por SSH sin contraseña al servidor (agrega tu clave pública).
3. Ejecuta el siguiente comando:

```bash
ansible-playbook -i hosts site.yml
```

> Nota: el servidor gestionado debe tener Ubuntu Server 24.04 y estar accesible por IP desde el nodo de control.

## 🔑 Credenciales de prueba (Samba)

- **Usuario:** `devuser1`
- **Contraseña:** `Innova.2025`
- **Recurso:** `smb://<ip_servidor>/Proyectos`

## 📸 Capturas incluidas en el informe

- Página web personalizada (`index.html`)
- Conexión al recurso compartido Samba
- Creación de archivo dentro de la carpeta `proyectos`

## 🧠 Autor

Kelly Darlyn Córdova Gutiérrez  
Taller de Sistemas Operativos II – UPDS  
Julio 2025
