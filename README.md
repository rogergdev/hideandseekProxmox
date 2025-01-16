# hideandseekProxmox

# Ocultar la Sección de "Subscriptions" en Proxmox

Este repositorio contiene instrucciones para ocultar la sección de "Subscriptions" en la interfaz web de Proxmox. Este cambio está dirigido a entornos sin suscripción y es útil para personalizar la experiencia visual.

---

## **Requisitos Previos**
- Acceso SSH al servidor Proxmox.
- Permisos de superusuario (`root`).

---

## **Pasos para Ocultar la Sección de "Subscriptions"**

### 1. Editar el Archivo CSS de Proxmox
El archivo CSS controla el diseño y la visualización de elementos en la interfaz web.

Ejecuta el siguiente comando para abrir el archivo:
```bash
nano /usr/share/pve-manager/css/ext6-pve.css
```

### 2. Añadir Reglas CSS para Ocultar la Sección
Al final del archivo, añade las siguientes reglas:
```css
#pveHealthWidget-1105 {
    display: none !important;
}

#panel-1104 {
    display: none !important;
}
```
Estas reglas ocultan tanto el contenido como el bloque principal de la sección de "Subscriptions".

### 3. Guardar y Salir
- Pulsa `Ctrl + O` para guardar.
- Pulsa `Enter` para confirmar.
- Pulsa `Ctrl + X` para salir del editor.

### 4. Reiniciar los Servicios de Proxmox
Reinicia el servicio de la interfaz web para aplicar los cambios:
```bash
systemctl restart pveproxy
```

### 5. Limpiar la Caché del Navegador
Fuerza la recarga completa de la página para reflejar los cambios:
- **Windows/Linux:** Pulsa `Ctrl + Shift + R`.
- **MacOS:** Pulsa `Cmd + Shift + R`.

---

## **Resultado Esperado**
Después de completar los pasos anteriores, la sección de "Subscriptions" debería desaparecer completamente de la interfaz web de Proxmox.

---

## **Notas**
- Este cambio no afecta la funcionalidad de Proxmox.
- En futuras actualizaciones de Proxmox, este archivo CSS podría ser sobrescrito. Si esto sucede, simplemente vuelve a aplicar los pasos descritos.

---

## **Advertencia**
Este cambio está destinado únicamente a entornos no comerciales y de prueba. Se recomienda adquirir una suscripción para soporte oficial y acceso a repositorios empresariales.
