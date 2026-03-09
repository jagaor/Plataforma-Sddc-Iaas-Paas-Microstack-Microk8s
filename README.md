# Creación de una Plataforma SDDC basada en IaaS y PaaS

## 📝 Descripción General
Este proyecto forma parte del módulo de "Bastionado de Redes y Sistemas". Consiste en configurar una plataforma de Software-Defined Data Center (SDDC) en un entorno virtualizado utilizando soluciones de Infraestructura como Servicio (IaaS) y Plataforma como Servicio (PaaS) con software libre. El entorno se ha desplegado sobre un equipo con recursos limitados de 16GB de RAM.

## 🎯 Objetivos
* Implementar una solución IaaS utilizando MicroStack.
* Desplegar una capa PaaS basada en Kubernetes utilizando MicroK8s.
* Lanzar una máquina virtual de prueba (CirrOS) y asignarle una IP flotante.
* Desplegar un servidor web Nginx en contenedores y exponer sus servicios.
* Configurar reglas de firewall (Security Groups) en el IaaS para permitir tráfico de red.

## 🛠️ Tecnologías y Herramientas
* **Gestor de Paquetes**: Snap.
* **IaaS (OpenStack)**: MicroStack.
  * Servicios integrados: Nova, Neutron, Keystone, Glance.
  * Panel de control: Horizon.
* **PaaS (Kubernetes)**: MicroK8s.
  * Addons: dns, dashboard, storage.

## ⚙️ Detalles de Implementación Destacados
* **Inicialización del Control Node**: La nube se inicializó con el comando de autoconfiguración para establecer el nodo como controlador principal.
* **Gestión de Seguridad IaaS**: Se configuraron reglas de Security Groups para permitir tráfico ICMP (ping) y conexiones SSH por el puerto TCP 22 hacia las instancias.
* **Optimización PaaS**: Se añadió el usuario actual al grupo de administración de MicroK8s para operar el clúster de forma ágil sin necesidad de escalar privilegios constantemente.
* **Despliegue de Cargas de Trabajo**: Se creó un "Deployment" llamado "mi-web" con la imagen de Nginx y se expuso a través del puerto 80 mediante NodePort. Se verificó el acceso al Kubernetes Dashboard mediante un proxy seguro.

## 📄 Documentación Completa
Para ver el paso a paso de los comandos ejecutados, el proceso de instalación y capturas de los paneles web de Horizon y el Dashboard de Kubernetes, consulta la memoria técnica completa del proyecto:

[Enlace al Informe Técnico en Google Drive](https://docs.google.com/document/d/14W98NpXzjYeaJ1s8btrgFALNjVrx9kPagh39gp2gVqs/edit?usp=sharing)

## ⚠️ Aviso Legal / Ética
*Este proyecto se ha realizado con fines puramente académicos y educativos.*
