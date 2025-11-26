# 🤖 Guía de Claude Code para Rueda de Negocios

**Sistema:** Rueda de Negocios v2.0
**Organización:** Nodo Bioceánico Central
**Fecha del Evento:** 28 de Noviembre, 2025

---

## 📋 Índice

1. [Introducción](#introducción)
2. [Estructura del Proyecto](#estructura-del-proyecto)
3. [Cómo Usar Claude Code](#cómo-usar-claude-code)
4. [Comandos Útiles](#comandos-útiles)
5. [Flujo de Desarrollo](#flujo-de-desarrollo)
6. [Tareas Comunes](#tareas-comunes)
7. [Resolución de Problemas](#resolución-de-problemas)
8. [Mejores Prácticas](#mejores-prácticas)

---

## 🎯 Introducción

Este documento sirve como guía para trabajar con el Sistema de Rueda de Negocios utilizando Claude Code. Claude puede ayudarte a entender, modificar y mejorar el código de forma eficiente.

### ¿Qué es este Sistema?

Sistema web de gestión de reuniones empresariales para eventos de networking B2B que permite:
- Gestión de 15 mesas físicas
- 4 bloques horarios de 15 minutos cada uno
- Coordinación entre empresas demandantes y oferentes
- Panel administrativo completo

### Stack Tecnológico

- **Backend:** PHP 7.4+ con PDO
- **Frontend:** HTML5, Tailwind CSS, JavaScript Vanilla
- **Base de Datos:** MySQL/MariaDB
- **Email:** PHPMailer
- **Seguridad:** Password hashing, prepared statements, sanitización

---

## 📁 Estructura del Proyecto

```
ruedaV2/
├── api/                          # Endpoints de la API
│   ├── login.php                 # Autenticación
│   ├── registro.php              # Registro de empresas
│   ├── reuniones.php             # Gestión de reuniones
│   ├── solicitar_reunion.php     # Solicitar reuniones
│   ├── guardar_disponibilidad.php # Guardar disponibilidad
│   ├── admin_reuniones.php       # Gestión administrativa
│   └── exportar.php              # Exportación de datos
│
├── views/                        # Vistas del frontend
│   ├── login.php                 # Página de login
│   ├── registro.php              # Formulario de registro
│   ├── panel-empresa-a.php       # Panel empresas demandantes
│   ├── panel-empresa-b.php       # Panel empresas oferentes
│   ├── panel-admin.php           # Panel de administración
│   └── wizard-disponibilidad.php # Configurar disponibilidad
│
├── config/                       # Configuración
│   └── config.php                # Configuración de BD y SMTP
│
├── includes/                     # Archivos compartidos
│   ├── db.php                    # Conexión a base de datos
│   ├── functions.php             # Funciones auxiliares
│   └── auth.php                  # Funciones de autenticación
│
├── assets/                       # Recursos estáticos
│   ├── css/                      # Estilos personalizados
│   ├── js/                       # Scripts JavaScript
│   └── img/                      # Imágenes
│
├── uploads/                      # Archivos subidos
│
├── vendor/                       # Dependencias de Composer
│
├── setup_database_dinamico.php   # Script de configuración de BD
├── crear-admin.php               # Crear usuario administrador
├── diagnostico.php               # Diagnóstico del sistema
├── generar_bloques.php           # Generar bloques horarios
├── reset_disponibilidad.php      # Resetear disponibilidad
├── composer.json                 # Dependencias PHP
└── DOCUMENTACION_COMPLETA.md     # Documentación completa
```

---

## 🤖 Cómo Usar Claude Code

### Comandos Básicos de Claude

Claude Code puede ayudarte con:

#### 1. Explorar el Código

```
"Muéstrame cómo funciona el sistema de autenticación"
"¿Dónde se valida la disponibilidad de mesas?"
"Explícame el flujo de solicitud de reuniones"
```

#### 2. Modificar Código

```
"Agrega validación de email en el formulario de registro"
"Corrige el bug en la asignación de mesas"
"Refactoriza la función de disponibilidad para mejorar el rendimiento"
```

#### 3. Crear Nuevas Funcionalidades

```
"Agrega un filtro por rubro en el panel de empresas oferentes"
"Crea una API para obtener estadísticas del evento"
"Implementa notificaciones en tiempo real"
```

#### 4. Resolver Problemas

```
"¿Por qué no se están guardando las reuniones?"
"Debug el error en la exportación CSV"
"Soluciona el problema de doble reserva de mesas"
```

#### 5. Optimización

```
"Optimiza las queries SQL en admin_reuniones.php"
"Mejora el rendimiento del mapa de mesas"
"Reduce las llamadas a la base de datos"
```

---

## 🔧 Comandos Útiles

### Configuración Inicial

```bash
# Instalar dependencias de Composer
composer install

# Configurar base de datos (ejecutar en navegador)
# http://localhost/ruedaV2/setup_database_dinamico.php

# Crear usuario administrador (ejecutar en navegador)
# http://localhost/ruedaV2/crear-admin.php

# Generar bloques horarios (ejecutar en navegador)
# http://localhost/ruedaV2/generar_bloques.php
```

### Git (Trabajar con Claude)

```bash
# Ver estado del repositorio
git status

# Ver cambios realizados
git diff

# Crear commit (Claude puede ayudarte con el mensaje)
git add .
git commit -m "Descripción del cambio"

# Enviar cambios
git push origin nombre-rama
```

### Diagnóstico

```bash
# Ejecutar diagnóstico del sistema (en navegador)
# http://localhost/ruedaV2/diagnostico.php

# Verificar migración de reuniones
# http://localhost/ruedaV2/verificar_migracion_ok.php

# Verificar tabla de reuniones
# http://localhost/ruedaV2/verificar_tabla_reuniones.php
```

---

## 🔄 Flujo de Desarrollo

### 1. Antes de Empezar

```
"Claude, ayúdame a entender cómo funciona [funcionalidad X]"
```

Claude explorará el código y te dará un resumen completo.

### 2. Planificar Cambios

```
"Necesito agregar [nueva funcionalidad]. ¿Cuál es la mejor manera de implementarla?"
```

Claude te sugerirá la arquitectura y archivos a modificar.

### 3. Implementar

```
"Implementa [funcionalidad] siguiendo las mejores prácticas del proyecto"
```

Claude escribirá el código manteniendo el estilo del proyecto.

### 4. Probar

```
"¿Qué casos de prueba debería considerar para esta funcionalidad?"
```

Claude te sugerirá escenarios de prueba.

### 5. Documentar

```
"Agrega comentarios y documentación a este código"
```

Claude documentará tu código de forma clara.

---

## 📝 Tareas Comunes

### Agregar Nueva Funcionalidad

**Ejemplo: Agregar filtro por fecha en el panel admin**

```
Tú: "Claude, necesito agregar un filtro por fecha en el panel de
     administración para ver reuniones de días específicos"

Claude: [Analizará el código existente]
        [Sugerirá dónde agregar el filtro]
        [Implementará el filtro en backend y frontend]
        [Actualizará la documentación]
```

### Corregir un Bug

**Ejemplo: Error en validación de disponibilidad**

```
Tú: "Hay un bug que permite reservar la misma mesa+bloque dos veces"

Claude: [Revisará el código de validación]
        [Identificará el problema]
        [Implementará la corrección]
        [Agregará validación adicional]
```

### Optimizar Consultas

**Ejemplo: Mejorar rendimiento del mapa de mesas**

```
Tú: "El mapa de mesas carga muy lento. ¿Puedes optimizarlo?"

Claude: [Analizará las queries actuales]
        [Identificará cuellos de botella]
        [Optimizará las consultas SQL]
        [Agregará índices si es necesario]
```

### Agregar Validaciones

**Ejemplo: Validar horarios del evento**

```
Tú: "Agrega validación para que no se puedan crear reuniones
     fuera del horario del evento (11:00 - 12:15)"

Claude: [Agregará validación en backend]
        [Agregará validación en frontend]
        [Actualizará mensajes de error]
```

---

## 🐛 Resolución de Problemas

### Problema: No se guardan las reuniones

**Pregunta a Claude:**
```
"Las reuniones no se están guardando en la base de datos.
 ¿Puedes ayudarme a debuggear?"
```

**Claude hará:**
1. Revisar el código de la API `solicitar_reunion.php`
2. Verificar las validaciones
3. Revisar las queries SQL
4. Identificar el problema
5. Proponer y aplicar la solución

### Problema: Emails no se envían

**Pregunta a Claude:**
```
"Los emails de notificación no se están enviando.
 ¿Puedes revisar la configuración de PHPMailer?"
```

**Claude hará:**
1. Revisar `config/config.php`
2. Verificar credenciales SMTP
3. Revisar el código de envío de emails
4. Sugerir correcciones
5. Implementar mejoras en el manejo de errores

### Problema: Error en el mapa de mesas

**Pregunta a Claude:**
```
"El mapa de mesas muestra información incorrecta.
 ¿Puedes revisar la lógica?"
```

**Claude hará:**
1. Revisar la query que obtiene los datos
2. Verificar la lógica de renderizado
3. Identificar discrepancias
4. Corregir el problema
5. Agregar validación adicional

---

## ✅ Mejores Prácticas

### Al Trabajar con Claude

1. **Sé Específico**
   - ❌ "Mejora el código"
   - ✅ "Optimiza la query SQL en api/admin_reuniones.php línea 45"

2. **Proporciona Contexto**
   - ❌ "Hay un error"
   - ✅ "Al crear una reunión como admin, aparece error 500. El log muestra..."

3. **Pide Explicaciones**
   - ✅ "¿Por qué usamos prepared statements aquí?"
   - ✅ "Explícame cómo funciona el constraint UNIQUE en disponibilidad_empresas"

4. **Valida los Cambios**
   - ✅ "¿Este cambio afectará otras partes del sistema?"
   - ✅ "¿Qué casos de prueba debería ejecutar?"

### Seguridad

**IMPORTANTE:** Siempre pide a Claude que:
- Valide inputs del usuario
- Use prepared statements
- Sanitice datos
- Verifique permisos de acceso
- No exponga información sensible

**Ejemplo:**
```
"Agrega esta funcionalidad asegurándote de:
 - Validar todos los inputs
 - Usar prepared statements
 - Verificar permisos del usuario
 - Sanitizar datos antes de mostrarlos"
```

### Código Limpio

**Pide a Claude que:**
- Siga el estilo del código existente
- Agregue comentarios en español
- Use nombres de variables descriptivos
- Mantenga funciones pequeñas y específicas

**Ejemplo:**
```
"Refactoriza esta función siguiendo el estilo del proyecto
 y agrega comentarios en español"
```

---

## 🎓 Ejemplos de Uso Avanzado

### Ejemplo 1: Agregar Exportación PDF

```
Tú: "Necesito agregar exportación de agenda en PDF además de CSV.
     Usa una librería compatible con PHP 7.4"

Claude: [Sugerirá usar TCPDF o similar]
        [Instalará vía Composer]
        [Creará nueva función de exportación]
        [Agregará botón en panel admin]
        [Mantendrá estructura de CSV existente]
```

### Ejemplo 2: Implementar WebSockets

```
Tú: "Quiero que las actualizaciones de reuniones se vean en
     tiempo real sin recargar la página"

Claude: [Analizará requisitos del servidor]
        [Sugerirá solución (Ratchet, Socket.io, etc)]
        [Implementará servidor WebSocket]
        [Actualizará frontend para escuchar eventos]
        [Documentará la nueva funcionalidad]
```

### Ejemplo 3: Migrar a Versión Moderna

```
Tú: "¿Puedes ayudarme a migrar este código a PHP 8.2
     manteniendo compatibilidad hacia atrás?"

Claude: [Identificará código deprecado]
        [Sugerirá cambios necesarios]
        [Implementará mejoras de PHP 8.2]
        [Agregará type hints]
        [Actualizará documentación]
```

---

## 📚 Recursos Adicionales

### Documentación del Proyecto

- **DOCUMENTACION_COMPLETA.md**: Documentación completa del sistema
- **Comentarios en código**: Explicaciones inline en archivos PHP
- **Base de datos**: Schema en `setup_database_dinamico.php`

### Preguntas Frecuentes a Claude

**Arquitectura:**
```
"Explícame la arquitectura de este sistema"
"¿Cómo se relacionan las tablas de la base de datos?"
"¿Cuál es el flujo completo desde registro hasta reunión?"
```

**Seguridad:**
```
"¿El sistema tiene vulnerabilidades de seguridad?"
"¿Cómo se previene SQL injection en este código?"
"¿Las contraseñas están correctamente hasheadas?"
```

**Performance:**
```
"¿Qué partes del sistema podrían optimizarse?"
"¿Hay queries N+1 en el código?"
"¿Cómo puedo mejorar el tiempo de carga del panel admin?"
```

**Extensibilidad:**
```
"¿Cómo puedo agregar un nuevo tipo de usuario?"
"¿Puedo agregar más bloques horarios sin romper el sistema?"
"¿Cómo implemento notificaciones push?"
```

---

## 🚀 Comandos Rápidos para Claude

### Exploración

```bash
# Entender una funcionalidad
"Explícame cómo funciona [X]"

# Ver relaciones
"¿Qué archivos usan esta función?"

# Buscar código
"¿Dónde se valida [Y]?"
```

### Modificación

```bash
# Agregar feature
"Implementa [funcionalidad] en [archivo]"

# Refactorizar
"Refactoriza [función] para mejorar [aspecto]"

# Corregir
"Corrige el bug en [ubicación]"
```

### Testing

```bash
# Probar código
"¿Qué casos de prueba debería considerar?"

# Validar cambios
"¿Este cambio puede romper algo?"

# Revisar
"Revisa este código y sugiere mejoras"
```

---

## 🎯 Próximos Pasos

### Después de Leer Esta Guía

1. **Explora el código** con Claude:
   ```
   "Claude, dame un tour del código del sistema de reuniones"
   ```

2. **Entiende el flujo**:
   ```
   "Explícame paso a paso qué pasa cuando una empresa
    solicita una reunión"
   ```

3. **Identifica mejoras**:
   ```
   "¿Qué mejoras sugieres para este sistema?"
   ```

4. **Empieza a desarrollar**:
   ```
   "Voy a implementar [X]. ¿Cuál es el mejor enfoque?"
   ```

---

## 📞 Soporte

### Trabajando con Claude

Si Claude no entiende algo:
- Proporciona más contexto
- Muéstrale el código relevante
- Explica qué intentaste hacer
- Describe el comportamiento esperado vs actual

### Limitaciones

Claude Code es excelente para:
- ✅ Escribir y modificar código
- ✅ Explicar funcionalidades
- ✅ Debuggear problemas
- ✅ Optimizar código
- ✅ Agregar features

Pero no puede:
- ❌ Ejecutar el código directamente
- ❌ Acceder a tu base de datos
- ❌ Ver tu servidor en ejecución
- ❌ Modificar archivos fuera del proyecto

---

## 📄 Versionado

**Versión de este documento:** 1.0
**Compatible con:** Rueda de Negocios v2.0
**Última actualización:** 26 de Noviembre, 2025

---

## 🎉 Conclusión

Claude Code es tu asistente de desarrollo que puede:
- Entender código complejo rápidamente
- Implementar funcionalidades siguiendo mejores prácticas
- Debuggear problemas difíciles
- Optimizar rendimiento
- Mantener consistencia en el código
- Documentar cambios

**Recuerda:** Claude es más efectivo cuando le das contexto claro y específico sobre lo que necesitas.

---

**¡Feliz desarrollo con Claude Code!** 🚀

*Para más información sobre el sistema, consulta DOCUMENTACION_COMPLETA.md*
