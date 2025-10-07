# AWS Secrets Manager CloudFormation Template

Esta plantilla de **AWS CloudFormation** automatiza la creación y gestión de secretos en **AWS Secrets Manager**, incluyendo políticas de acceso seguras, etiquetas de identificación y cifrado mediante **AWS KMS**.

---

## 🧱 Descripción General

El objetivo de esta plantilla es estandarizar y automatizar la creación de secretos dentro de AWS, garantizando que todos los valores sensibles (credenciales, tokens, claves, etc.) se almacenen de forma **segura, auditada y cifrada**.  
Permite integrar de manera sencilla nuevos secretos con etiquetas personalizadas y control de acceso mediante roles de IAM.

---

## ⚙️ Recursos Implementados

- **AWS::SecretsManager::Secret** → Crea el secreto en AWS Secrets Manager.  
- **AWS::SecretsManager::ResourcePolicy** → Aplica una política que restringe el acceso a roles o cuentas específicas.  
- **AWS KMS (Key Management Service)** → Cifra el contenido del secreto utilizando una clave KMS definida.  

---

## 🧩 Parámetros

| Parámetro | Descripción | Ejemplo |
|------------|-------------|----------|
| `CentroCosto` | Centro de costos asociado al componente. | `9302` |
| `NombreProyecto` | Nombre del proyecto o servicio. | `NombreServicio` |
| `Ambiente` | Ambiente de despliegue (`dev`, `qa`, `prod`). | `prod` |
| `idAplicativo` | Identificador único del aplicativo. | `idaplicativo` |
| `responsable` | Responsable o contacto principal. | `John Doe` |
| `lineanegocio` | Línea de negocio o unidad. | `Lineanegocio` |
| `ROLEARN` | ARN del rol autorizado a obtener el secreto. | `arn:aws:iam::<ACCOUNT_ID>:role/<ROLE_NAME>` |
| `jsonSecret` | Secreto en formato JSON (no incluir valores reales en GitHub). | `{ "username": "user", "password": "pass" }` |

---

## 🚀 Despliegue

Puedes desplegar esta plantilla directamente desde la **Consola de AWS**:

### Opción 1 – Consola de AWS
1. Abre [AWS CloudFormation](https://console.aws.amazon.com/cloudformation/home).  
2. Crea un nuevo *stack* y carga este archivo YAML.  
3. Completa los parámetros solicitados.  
4. Espera a que la creación finalice correctamente.
