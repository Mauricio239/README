
> [!NOTE]
>## ADMINISTRACION

 
> [!IMPORTANT]
>## Requerimientos de Software: </br> _Roles del Administrador de la App_

:+1: <font color="green"> Descripción General </font>
<font color='red'>rojo</font>


Este documento describe las **funcionalidades** y *responsabilidades* del administrador dentro de la aplicación, 
enfocándose en la gestión de usuarios. A continuación, se detallan los pasos y consideraciones necesarias para la creación y 
gestión de usuarios desde el Panel de Administración.

---

## Funcionalidades del Administrador 

### 1. Inicio de Sesión en el Panel de Administración 
1. **Ingresar credenciales de administrador** (`usuario` y `contraseña`).
2. Verificar permisos de acceso al módulo de gestión de usuarios.

> *Nota:* Asegúrate de que las credenciales sean correctas para evitar bloqueos de cuenta.

![Login Screen](https://img.freepik.com/vector-gratis/plantilla-login_1017-6719.jpg) </br>
*Ejemplo de pantalla de inicio de sesión*

### 2. Acceso al Módulo de Gestión de Usuarios 
- Navegar hasta la sección correspondiente en el menú principal.

### 3. Crear Nuevo Usuario 
- Hacer clic en el botón **"Nuevo Usuario"** o similar.

### 4. Formulario de Registro 

**Datos Personales:**
- Nombre completo.
- Apellido.
- Fecha de nacimiento.
- Sexo.
- Nacionalidad.
- Dirección completa.
- Teléfono celular.
- Correo electrónico.

**Datos Laborales:**
- Puesto (conductor profesional).
- Área de desempeño (transporte de carga, pasajeros, etc.).
- Fecha de ingreso a la empresa.

**Datos de Licencia:**
- Número de licencia.
- Categoría de licencia.
- Fecha de vencimiento.
- Organismo emisor.

**Datos Sensibles:**
- Número de DNI.
- Copia digitalizada del DNI (frente y dorso).
- Libreta sanitaria (número, fecha de vencimiento, organismo emisor).
- Antecedentes penales (si aplica, presentar certificado y validar los datos de la misma).

**Datos de Acceso:**
- Nombre de usuario (sugerir una combinación de nombre y apellido o iniciales).
- Contraseña (establecer políticas de seguridad: mínimo 8 caracteres, combinación de mayúsculas, minúsculas y números).
- Confirmar contraseña.

**Adjuntos:**
- Imagen de perfil.
- Foto carnet.

### 5. Validación de Datos 
- [x] Verificar que todos los campos obligatorios estén completados.
- [x] Validar la sintaxis de los datos ingresados (por ejemplo, formato de correo electrónico, número de teléfono).
- [x] Comprobar la autenticidad de los documentos adjuntos.

### 6. Asignación de Permisos 
1. Definir los permisos específicos para el perfil de conductor (acceso a rutas, vehículos, etc.).
2. Asignar el conductor a un vehículo o flota determinada.

### 7. Notificación al Usuario 
- [ ] Enviar un correo electrónico al nuevo usuario con sus credenciales de acceso y un enlace para cambiar la contraseña inicial.
- [ ] Enviar una notificación push a la app móvil del administrador confirmando la creación del usuario.

### 8. Guardado de la Información 
- Almacenar los datos del usuario en la base de datos de la aplicación.
- **Cifrar** los datos sensibles (DNI, libreta sanitaria, antecedentes penales).

### 9. Finalización del Proceso 
- Mostrar un mensaje de confirmación al administrador indicando que el usuario ha sido creado exitosamente.

---
> [!IMPORTANT]
> ## Consideraciones Adicionales 

### Flujo de Aprobación ###
- Implementar un flujo de aprobación para la creación de nuevos usuarios, especialmente para perfiles con acceso a datos sensibles.

### Historial de Modificaciones 
- Registrar todas las modificaciones realizadas a los datos de un usuario para mantener una auditoría.

### Seguridad
- Asegurar la confidencialidad y la integridad de los datos mediante el uso de protocolos de seguridad robustos y el cumplimiento de las normativas actuales de protección de datos.

### Escalabilidad
- Diseñar el sistema para que pueda manejar un gran volumen de usuarios y datos.

### Usabilidad
- Crear una interfaz intuitiva y fácil de usar para los administradores y usuarios finales.

---
> [!TIP]
> ## Ejemplo de JSON de Usuario 
```json
{
  "firstName": "Juan",
  "lastName": "Pérez",
  "birthdate": "1985-06-15",
  "role": "Conductor",
  "license": {
    "number": "ABC123456",
    "category": "C",
    "expiryDate": "2025-12-31"
  },
  "credentials": {
    "username": "jperez",
    "password": "SecurePass123"
  }
}
