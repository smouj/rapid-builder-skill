description: Herramienta de automatización de infraestructura impulsada por IA para el despliegue rápido y configuración de recursos en la nube, redes y servicios
tags: [infrastructure, ai, automation, cloud, devops]
version: 1.0.0
author: OpenClaw Team
created: 2026-03-15
updated: 2026-03-15
category: Infrastructure
dependencies: [aws-cli, terraform, ansible, docker, kubectl]
environment_vars:
  - RAPID_BUILDER_API_KEY: Clave API requerida para la integración del servicio de IA
  - RAPID_BUILDER_CLOUD_PROVIDER: Proveedor de nube predeterminado (aws/azure/gcp)
  - RAPID_BUILDER_REGION: Región de despliegue predeterminada
  - RAPID_BUILDER_DRY_RUN: Habilitar modo de ejecución en seco para validación sin ejecución
---

# Rapid Builder

## Purpose

Rapid Builder es un marco de automatización de infraestructura impulsado por IA diseñado para acelerar el despliegue y la gestión de infraestructura en la nube, orquestación de contenedores y configuraciones de red. Utiliza modelos avanzados de IA para interpretar requisitos en lenguaje natural y generar plantillas ejecutables de infraestructura como código (IaC), scripts de despliegue y flujos de trabajo operativos.

### Real Use Cases

1. **Multi-Cloud Service Deployment**: Proporciona automáticamente una pila de aplicaciones web en AWS ECS, Azure Kubernetes Service y GCP Cloud Run basada en una descripción simple como "Deploy a Node.js API with PostgreSQL database and Redis cache in production environment with auto-scaling".

2. **Network Security Hardening**: Genera y aplica reglas de firewall, configuraciones VPN y sistemas de detección de intrusiones para entornos híbridos en la nube, respondiendo a consultas como "Secure our VPC with least-privilege access for microservices communication".

3. **CI/CD Pipeline Infrastructure**: Construye pipelines completos de CI/CD incluyendo Jenkins, GitLab CI o GitHub Actions con escaneo de seguridad integrado, configuración de registro de contenedores y estrategias de despliegue para arquitecturas de microservicios.

4. **Disaster Recovery Setup**: Automatiza la creación de estrategias de respaldo, configuraciones de failover y replicación entre regiones para bases de datos críticas y aplicaciones con estado.

5. **IoT Edge Computing Infrastructure**: Despliega y configura nodos de computación en el borde con orquestación de contenedores, monitoreo y canales de comunicación seguros para sistemas IoT distribuidos.

## Alcance

Rapid Builder opera dentro del dominio de la infraestructura, enfocándose en el aprovisionamiento automatizado, configuración y gestión de recursos en la nube. Se integra con proveedores de nube principales y herramientas de infraestructura mientras mantiene las mejores prácticas de seguridad y optimización de costos.

### Specific Commands

- `rapid-builder analyze <requirements>`: Análisis impulsado por IA de requisitos de infraestructura a partir de descripciones en lenguaje natural
- `rapid-builder generate <type> --provider <aws|azure|gcp> --environment <dev|staging|prod>`: Genera plantillas IaC (Terraform, CloudFormation, ARM templates)
- `rapid-builder validate <template>`: Análisis estático y validación de seguridad de plantillas generadas
- `rapid-builder deploy <template> --dry-run --rollback-on-failure`: Ejecuta despliegue con opción de dry-run y rollback automático
- `rapid-builder monitor <resource-id> --metrics <cpu|memory|network> --alert-threshold <value>`: Monitoreo en tiempo real y alertas para recursos desplegados
- `rapid-builder optimize <resource-id> --cost-target <budget> --performance-priority <high|medium|low>`: Optimización de recursos impulsada por IA para costo y rendimiento
- `rapid-builder backup <resource-id> --strategy <incremental|full> --retention <days>`: Configuración y ejecución automatizada de respaldos
- `rapid-builder scale <service> --min-instances <n> --max-instances <n> --metric <cpu-utilization>`: Automatización de escalado horizontal y vertical
- `rapid-builder audit <resource-id> --compliance <pci-dss|hipaa|soc2>`: Auditoría y reporte de cumplimiento

### Limitations

- No maneja generación de código a nivel de aplicación o lógica de negocio
- Requiere credenciales válidas de proveedor de nube y acceso API
- Limitado a proveedores de nube soportados (AWS, Azure, GCP) y herramientas de infraestructura
- No realiza aprovisionamiento de hardware físico
- El código generado por IA requiere revisión humana para escenarios empresariales complejos

## Proceso de Trabajo

Rapid Builder sigue un flujo de trabajo estructurado y asistido por IA para asegurar despliegues de infraestructura confiables:

### 1. Requirements Analysis (AI-Powered)
- Analiza requisitos en lenguaje natural usando modelos NLP
- Identifica componentes de infraestructura, dependencias y restricciones
- Genera especificaciones técnicas detalladas con estimaciones de costo
- Valida requisitos contra estándares de seguridad y cumplimiento

### 2. Template Generation
- Selecciona el marco IaC apropiado basado en proveedor y complejidad
- Genera plantillas modulares y reutilizables con etiquetado adecuado de recursos
- Incorpora mejores prácticas para seguridad, monitoreo y escalabilidad
- Incluye scripts de gestión de configuración (Ansible playbooks, shell scripts)

### 3. Validation Phase
- Validación sintáctica y semántica del código generado
- Escaneo de seguridad para vulnerabilidades y configuraciones erróneas
- Análisis de costo y verificación de cumplimiento de presupuesto
- Resolución de dependencias y verificación de compatibilidad

### 4. Deployment Execution
- Aprovisionamiento paralelo de recursos usando APIs de proveedor
- Aplicación de gestión de configuración
- Configuración de verificación de salud y descubrimiento de servicios
- Integración con sistemas existentes de monitoreo y logging

### 5. Optimization and Monitoring
- Establecimiento de línea base de rendimiento
- Implementación de políticas de escalado automatizadas
- Recomendaciones de optimización de costo
- Monitoreo continuo con detección de anomalías impulsada por IA

### 6. Documentation and Handover
- Genera documentación comprehensiva
- Crea runbooks para equipos de operaciones
- Establece procedimientos de gestión de cambios
- Actualizaciones de base de conocimientos para despliegues futuros

## Reglas de Oro

1. **Security First**: Toda infraestructura generada debe pasar escaneos de seguridad automatizados y cumplir con benchmarks CIS antes del despliegue.

2. **Cost Awareness**: Toda asignación de recursos incluye validación de presupuesto y sugerencias de optimización para prevenir cargos inesperados.

3. **Idempotency Guarantee**: Las plantillas generadas deben ser idempotentes, permitiendo re-ejecución segura sin efectos secundarios.

4. **Rollback Preparedness**: Todo despliegue incluye procedimientos de rollback automatizados y snapshots de estado para recuperación rápida.

5. **Compliance Integration**: Los diseños de infraestructura incorporan marcos de cumplimiento relevantes (GDPR, HIPAA, PCI-DSS) basados en requisitos especificados.

6. **Monitoring by Default**: Todos los despliegues incluyen configuraciones comprehensivas de monitoreo, logging y alertas desde el inicio.

7. **Version Control Everything**: Todo código generado, configuraciones y artefactos de despliegue se commitean a control de versiones con versionado semántico.

8. **Zero-Trust Architecture**: Implementa segmentación de red, acceso de privilegio mínimo y encriptación en todas partes por defecto.

9. **Performance Benchmarking**: Establece y rastrea líneas base de rendimiento con pruebas automatizadas para detección de regresiones.

10. **Documentation Automation**: Genera documentación técnica, especificaciones API y runbooks operativos como parte de cada despliegue.

## Examples

### Example 1: Deploying a Microservices Architecture

**User Input:**
```
rapid-builder analyze \"Deploy a microservices e-commerce platform with API gateway, user service, product catalog, order processing, and payment integration on AWS. Use ECS for container orchestration, RDS for databases, and ElastiCache for caching. Include monitoring with CloudWatch and security groups for network isolation.\"
```

**Generated Output:**
```yaml
# Generated Terraform template excerpt
resource \"aws_ecs_cluster\" \"ecommerce\" {
  name = \"ecommerce-cluster\"
  
  setting {
    name  = \"containerInsights\"
    value = \"enabled\"
  }
}

resource \"aws_security_group\" \"api_gateway\" {
  name_prefix = \"api-gateway-\"
  vpc_id      = aws_vpc.main.id

  ingress {
    from_port   = 443
    to_port     = 443
    protocol    = \"tcp\"
    cidr_blocks = [\"0.0.0.0/0\"]
  }
}
```

**Execution:**
```
rapid-builder deploy ecommerce-platform.tf --provider aws --environment production --rollback-on-failure
```

### Example 2: Network Security Configuration

**User Input:**
```
rapid-builder generate firewall --provider azure --environment production \"Create network security groups for a three-tier web application with strict access controls and threat protection\"
```

**Generated Output:**
```json
{
  \"properties\": {
    \"securityRules\": [
      {
        \"name\": \"AllowHTTPS\",
        \"properties\": {
          \"priority\": 100,
          \"access\": \"Allow\",
          \"direction\": \"Inbound\",
          \"sourceAddressPrefix\": \"*\",
          \"sourcePortRange\": \"*\",
          \"destinationAddressPrefix\": \"*\",
          \"destinationPortRange\": \"443\",
          \"protocol\": \"Tcp\"
        }
      }
    ]
  }
}
```

**Verification:**
```
rapid-builder validate network-security.json --compliance pci-dss
# Output: Validation passed. 0 security issues found. Estimated cost: $15.30/month
```

### Example 3: Disaster Recovery Setup

**User Input:**
```
rapid-builder backup production-database --strategy incremental --retention 30 --cross-region-replication
```

**Generated Output:**
```
# Backup configuration created
- Incremental backups: Daily at 02:00 UTC
- Full backups: Weekly on Sundays
- Cross-region replication: us-east-1 → us-west-2
- Retention policy: 30 days
- Encryption: AES-256 with KMS
- Monitoring: CloudWatch alarms for backup failures
```

## Rollback Commands

### Deployment Rollback
```
rapid-builder rollback <deployment-id> --reason \"Failed health checks\" --preserve-data
```
- Revierte infraestructura a estado estable anterior
- Preserva volúmenes de datos persistentes y bases de datos
- Registra acciones de rollback para auditorías

### Configuration Rollback
```
rapid-builder config-rollback <service-name> --version <previous-version> --dry-run
```
- Revierte cambios de configuración sin afectar instancias en ejecución
- Soporta estrategias de rollback de despliegue canary
- Valida sintaxis de configuración antes de aplicación

### Resource Cleanup
```
rapid-builder cleanup <resource-pattern> --force --skip-dependencies
```
- Remueve recursos huérfanos e infraestructura no utilizada
- Soporta patrones regex para limpieza selectiva
- Incluye prompts de confirmación para operaciones destructivas

### State Reset
```
rapid-builder reset-state <environment> --backup-first --confirm
```
- Resetea estado de Terraform a configuración conocida buena
- Crea snapshots de respaldo antes de reset
- Requiere confirmación explícita para entornos de producción

## Dependencies and Requirements

### Requisitos del Sistema
- Python 3.9+
- 4GB RAM mínimo, 8GB recomendado
- 10GB espacio libre en disco
- Soporte Linux/Windows/macOS

### Cloud Provider Requirements
- AWS: Usuario IAM con AdministratorAccess o equivalente
- Azure: Rol Contributor en suscripción
- GCP: Rol Editor en proyecto

### API Requirements
- Clave API válida para integración de servicio de IA
- Herramientas CLI de proveedor de nube instaladas y configuradas
- Claves SSH para acceso a bastion host

## Verification Steps

### Post-Deployment Verification
1. Existencia de recursos: `rapid-builder verify <deployment-id> --check resources`
2. Salud del servicio: `rapid-builder verify <deployment-id> --check health`
3. Cumplimiento de seguridad: `rapid-builder verify <deployment-id> --check security`
4. Benchmarks de rendimiento: `rapid-builder verify <deployment-id> --check performance`
5. Validación de costo: `rapid-builder verify <deployment-id> --check costs`

### Automated Testing
- Pruebas de infraestructura usando Terratest o marcos similares
- Pruebas de integración para comunicación de servicios
- Pruebas de carga con umbrales configurados
- Escaneo de seguridad con remediación automatizada

## Solución de Problemas

### Common Issues

1. **API Rate Limiting**
   - Síntoma: Errores de "Rate limit exceeded"
   - Solución: Implementar backoff exponencial, reducir concurrencia
   - Prevención: Monitorear uso API e implementar gestión de cuotas

2. **Resource Quota Exceeded**
   - Síntoma: "Quota exceeded" durante despliegue
   - Solución: Solicitar aumentos de cuota u optimizar asignación de recursos
   - Prevención: Verificar cuotas antes del despliegue con `rapid-builder quota-check`

3. **Dependency Resolution Failures**
   - Síntoma: Errores de "Circular dependency" o "Missing dependency"
   - Solución: Revisar plantillas generadas para dependencias lógicas
   - Prevención: Usar herramientas de visualización de dependencias

4. **Security Scan Failures**
   - Síntoma: Despliegue bloqueado por violaciones de seguridad
   - Solución: Revisar y remediar hallazgos de seguridad
   - Prevención: Ejecutar escaneos de seguridad durante generación de plantillas

5. **Cost Overruns**
   - Síntoma: Cargos inesperados en facturación de nube
   - Solución: Implementar alertas de costo y controles de presupuesto
   - Prevención: Usar estimaciones de costo y flujos de aprobación

### Debug Mode
Habilitar logging detallado para solución de problemas:
```
export RAPID_BUILDER_LOG_LEVEL=DEBUG
rapid-builder deploy template.tf --verbose
```

### Support Escalation
Para problemas críticos de producción, escalar al equipo de infraestructura con:
- ID de despliegue y logs
- Mensajes de error y stack traces
- Snapshot del estado actual de infraestructura
- Cambios recientes y hashes de commit

## Integration Points

- **CI/CD Systems**: GitHub Actions, Jenkins, GitLab CI
- **Monitoring**: Prometheus, Grafana, CloudWatch
- **Security**: AWS Config, Azure Policy, GCP Security Command Center
- **Cost Management**: AWS Cost Explorer, Azure Cost Management, GCP Billing
- **Configuration Management**: Ansible, Puppet, Chef

## Future Enhancements

- Despliegues híbridos multi-nube
- Escalado predictivo impulsado por IA
- Reportes automatizados de cumplimiento
- Integración con plataformas de computación en el borde
- Encriptación resistente a cuánticos para cargas de trabajo sensibles

---

*Esta skill es mantenida por el equipo de infraestructura de OpenClaw. Para contribuciones o reportes de bugs, por favor envíe issues al repositorio de OpenClaw.*