# 📄 Documentación del sistema

Cualquiera que sea el sistema elegido para su implantación, **debe estar oportunamente documentado**, incluyendo:

- Diagramas de procesos
- Identificación de funciones y responsables de tareas
- Políticas, normas internas y descripciones de procesos
- Registros escritos, actualizados y trazables

En nuestro modelo, se debe **acreditar que cada decisión de la empresa se ajusta al Derecho vigente y a las normas internas**, con evidencias de:

- **Políticas documentadas**
- **Controles implementados y su seguimiento**
- **Registro de todas las acciones realizadas**

> Los controles utilizados deben ser formales y documentados, dejando evidencia de todo lo realizado.

## 🔄 Actualización y supervisión

- Mantener el sistema **actualizado y demostrar su eficacia continuamente**
- El **Código Ético** será la norma principal, complementado con políticas y procesos que reflejen el modo de hacer de la organización
- Todo debe ser **trazable**, con evidencias de cumplimiento y controles disponibles ante requerimientos de autoridad
- Someter el modelo a **supervisión y revisiones periódicas** para testar su eficacia

## 🧩 Otros elementos documentados

- Gestión del **canal de denuncias**
- Sistema disciplinario y **sanciones aplicadas**

> Una documentación completa garantiza **transparencia**, facilita **auditorías** y asegura que la organización puede demostrar su **cumplimiento normativo** de manera objetiva

---

## Práctica: CISO Assistant — San Clemente Solutions

---

### 🏢 Contexto

San Clemente Solutions es una empresa tecnológica que desarrolla software de gestión para PYMES. La empresa ha crecido recientemente y necesita formalizar su sistema de seguridad, incluyendo gestión de riesgos, controles documentados y auditorías periódicas.

Se decide implantar **CISO Assistant** como herramienta centralizada.

**Objetivos de la práctica:**
- Configurar desde cero la organización en CISO Assistant.
- Definir roles, usuarios y grupos.
- Identificar riesgos y construir una matriz de riesgos.
- Aplicar un framework de seguridad.
- Realizar una auditoría inicial (interna y externa).

---

### 📝 Tareas a realizar

#### 1. Crear la organización y dominios
- Nombre de la organización: `San Clemente Solutions`.
- Dominio corporativo principal: `SanClemente`.

#### 2. Configurar perímetros de seguridad
- **Perímetro interno (On-Premise)**  
  - Servidores en oficina, LAN, switches, almacenamiento interno.  
  - ERP interno usado por Administración.
- **Perímetro nube (Cloud Services)**  
  - Elegir plataforma: AWS / Azure / GCP.  
  - Contiene aplicaciones de desarrollo, base de datos de clientes y web corporativa.
- **Opcional:** Perímetro dispositivos móviles/teletrabajo  
  - Portátiles corporativos, acceso VPN, BYOD si aplica.

#### 3. Crear usuarios y grupos
- Usuarios mínimos (roles en CISO Assistant y empresa):

| Usuario                 | Rol en empresa         | Rol CISO Assistant |
|-------------------------|----------------------|------------------|
| Dirección General       | Toma decisiones      | Manager          |
| CISO_SanClemente        | Responsable seguridad | Admin            |
| Técnico de Sistemas     | Operaciones IT       | Editor           |
| Auditor Externo         | Revisión y control   | Viewer / Auditor |
| DPO_SanClemente         | Cumplimiento GDPR    | Editor           |

- Grupos mínimos:
  - **Equipo de Seguridad:** CISO + Técnico
  - **Auditoría y Cumplimiento:** Auditor + Dirección

#### 4. Identificación y análisis de riesgos
- Identificar mínimo 5 riesgos asignados a perímetros.
- Crear **matriz de riesgos 3×3 o 5×5** (probabilidad × impacto).
- Ejemplos:
  - Fuga de datos en cloud.
  - Acceso no autorizado a servidores internos.
  - Malware en teletrabajo.
  - Vulnerabilidad en la aplicación web.
  - Interrupción del servicio por fallo eléctrico.
- Para cada riesgo: causa, activos afectados, medidas preventivas, responsable.

#### 5. Aplicación de un framework
- Elegir uno: ISO 27001:2022, ENS, NIST SP 800-53.
- Crear controles y asociar mínimo 8 a riesgos identificados.
- Indicar estado de implantación: Implementado / Parcial / Pendiente.

#### 6. Auditoría inicial
- Auditoría interna y externa.
- Evaluar controles por áreas clave: políticas, accesos, continuidad, operación de sistemas.
- Añadir mínimo 3 evidencias.
- Generar informe final (borrador aceptable).

---

## SOLUCIÓN / TUTORIAL

### 1. Crear la organización
1. Acceder a **Settings → Organization Settings**.
2. Crear organización:
   - **Name:** San Clemente Solutions
   - Industria: Tecnología y servicios cloud
   - Descripción: SaaS para PYMES

### 2. Crear el dominio principal
1. **Domains → + Create new domain**
2. Datos:
   - **Name:** SanClemente_DominioPrincipal
   - **Manager:** ResponsableSeguridadTI (o tu usuario)
3. Guardar cambios.

### 3. Crear perímetros
#### 3.1 Perímetro interno
- **Name:** Perímetro_Interno_OficinaCentral
- **Scope:** Internal perimeter
- **Responsable:** ITManager
- **Descripción:** LAN, servidores internos y ERP

#### 3.2 Perímetro cloud
- **Name:** Perímetro_Cloud_Azure
- **Scope:** External perimeter
- **Responsable:** CloudAdmin
- **Descripción:** Aplicaciones, DB clientes, web corporativa

#### 3.3 Perímetro opcional
- Dispositivos móviles / teletrabajo

### 4. Usuarios, roles y grupos
#### 4.1 Usuarios
- Users → Add new user:

| Usuario            | Rol principal             | Descripción                              |
|-------------------|---------------------------|-------------------------------------------|
| CISO_SanClemente  | CISO                      | Responsable global de seguridad           |
| CloudAdmin        | Cloud Manager             | Administra Azure                          |
| ITManager         | Network & Systems Manager | Gestor de redes y sistemas                |
| Auditor_Externo   | Auditor                   | Revisor independiente                     |
| DPO_SanClemente   | Data Protection Officer   | Cumplimiento GDPR                          |

#### 4.2 Grupos
- Grupo_Seguridad → CISO_SanClemente, ITManager
- Grupo_Cloud → CloudAdmin
- Grupo_Auditoria → Auditor_Externo
- Grupo_Compliance → DPO_SanClemente

### 5. Matriz de riesgos y registro
1. **Crear matriz 5×5**
   - Risk Management → Settings → Risk Matrices → + Create
   - Likelihood: 1–5, Impact: 1–5
2. **Registrar riesgos**
- R1: Acceso no autorizado portal SaaS (Cloud)
- R2: Caída servidor base de datos (Cloud)
- R3: Malware en red interna (Interno)
- R4: Vulnerabilidad web (Cloud)
- R5: Corte eléctrico (Interno)

Para cada riesgo:
- Causa, activos afectados, medidas preventivas, responsable

### 6. Framework de seguridad
1. **Compliance → Frameworks → + Add** → ISO 27001:2022
2. Crear evaluación: Audits → Compliance Assessments → + Create
   - Scope: dominio + ambos perímetros
   - Auditor: Auditor_Externo
   - Evaluar controles (A.5, A.8, A.12, A.16)

### 7. Auditoría inicial
#### 7.1 Auditoría interna
- Audits → + New audit
- Scope: Perímetro interno + políticas
- Evaluar 1–2 controles por área: accesos, antivirus, inventario
- Subir evidencias: PDF/capturas

#### 7.2 Auditoría externa
- Scope: Perímetro cloud + ISO 27001
- Auditor: Auditor_Externo
- Revisar: seguridad SaaS, protección datos, gestión incidentes

### 8. Entregables
- Capturas dominio/perímetros y usuarios/grupos
- Export matriz de riesgos
- Listado controles con estado
- Informe de auditoría (PDF)
- Justificación breve (≤10 líneas)


