# 📋 Reporte Médico para WhatsApp

## Descripción General

Este script de Python procesa y formatea reportes médicos del área de Emergencias de un Hospital General, específicamente para la especialidad de Medicina Interna, generando un formato optimizado para compartir por WhatsApp.

## 🎯 Funcionalidades Principales

### 1. Procesamiento de Datos de Pacientes

* Pacientes Coordinados: Pacientes que ya tienen cama asignada.
* Pacientes Pendientes: Pacientes que esperan ingreso, organizados por fecha.

### 2. Características de Formateo

#### 🔤 Expansión de Abreviaturas Médicas

Convierte automáticamente abreviaturas médicas comunes a su significado completo:

* HTA → Hipertensión arterial
* DM2 → Diabetes Mellitus tipo 2
* EPOC → Enfermedad pulmonar obstructiva crónica
* etcétera...

#### 📍 Traducción de Ubicaciones

* h, hidrat, hid → HIDRATACIÓN
* o, obs → OBSERVACIÓN
* vc → VIGILANCIA CRÍTICA

#### 👤 Formateo de Nombres

Convierte nombres al formato: APELLIDOS, NOMBRE

#### 📝 Formato de Entrada Esperado

Para Pacientes Coordinados:

```
Nombre Paciente... Diagnóstico. Lugar Cama
```

Ejemplo:

```
Juan Pérez... HTA, DM2. o 12
María García Dx IVU. h 5
```

Para Pacientes Pendientes:

```
Fecha (DD/MM)
Paciente... Diagnóstico. CN/SN Comentario
```
3
Ejemplo:

```
15/12
Carlos López... EPOC. sn
Ana Torres Dx IRA. cn Estable
```

#### 🖥️ Uso del Programa

1. Ejecutar el script.
2. Pegar el texto plano con los datos de los pacientes.
3. Presionar Ctrl+D (Linux/Mac) o Ctrl+Z + Enter (Windows).
4. El programa generará automáticamente el reporte formateado.

#### 📊 Ejemplo de Salida

```markdown
🏥 *GUARDIA 15/12/2024 PM*

📝 *INGRESOS COORDINADOS*

1. PÉREZ, JUAN
_Diagnóstico: Hipertensión arterial, Diabetes Mellitus tipo 2_
→ 🛏️ *OBSERVACIÓN, CAMA 12*

2. GARCÍA, MARÍA
_Diagnóstico: Infección de vías urinarias_
→ 🛏️ *HIDRATACIÓN, CAMA 5*

⚕️ *INGRESOS PENDIENTES DE MEDICINA INTERNA*

*15/12/2024*
1. LÓPEZ, CARLOS
_Diagnóstico: Enfermedad pulmonar obstructiva crónica_
❌ Sin nota

2. TORRES, ANA
_Diagnóstico: Insuficiencia respiratoria aguda_
✅ Con nota
💬 Estable.
```

#### 🛠️ Características Técnicas

Módulos Utilizados

* re: Para expresiones regulares
* os: Para limpieza de pantalla
* sys: Para manejo del sistema
* datetime: Para manejo de fechas y turnos

Funciones Clave

* expandir_abreviaturas(): Convierte abreviaturas médicas
* procesar_linea_paciente(): Parsea cada línea de paciente
* generar_reporte(): Genera el reporte final formateado
* obtener_fecha_turno(): Determina automáticamente fecha y turno

#### 🏥 Contexto Hospitalario

Este sistema está diseñado específicamente para:

* Hospital: General
* Área: Emergencias
* Especialidad: Medicina Interna
* Propósito: Comunicación eficiente del estado de ingresos entre el personal médico

#### 💡 Beneficios

* ✅ Estandariza la comunicación médica
* ✅ Automatiza la expansión de terminología
* ✅ Optimiza para plataformas móviles (WhatsApp)
* ✅ Mejora la legibilidad de reportes
* ✅ Organiza información por prioridad y fecha
