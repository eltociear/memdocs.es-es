---
title: Control de acceso basado en rol (RBAC) con Microsoft Intune
description: Obtenga información la manera en que RBAC le permite controlar quién puede realizar acciones y cambios en Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0a0b1913b200c8316be98cc7df5de4b8d63d0d18
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88911444"
---
# <a name="role-based-access-control-rbac-with-microsoft-intune"></a>Control de acceso basado en rol (RBAC) con Microsoft Intune

El control de acceso basado en rol (RBAC) ayuda a administrar quién tiene acceso a los recursos de la organización y qué se puede hacer con dichos recursos.  Mediante la [asignación de roles](assign-role.md) a los usuarios de Intune, puede limitar lo que pueden ver y cambiar. Cada rol tiene un conjunto de permisos que determinan a qué pueden acceder y qué pueden cambiar dentro de la organización los usuarios con dicho rol.

Para crear, editar o asignar roles, la cuenta debe tener uno de los siguientes permisos en Azure AD:
- **Administrador global**
- **Administrador del servicio Intune** (también conocido como **Administrador de Intune**)

Para obtener consejos y sugerencias sobre la RBAC en Intune, puede ver esta serie de cinco vídeos en los que se muestran ejemplos y tutoriales: [1](https://www.youtube.com/watch?v=5deXLMLcnKY), [2](https://www.youtube.com/watch?v=38dnMBLuxbQ), [3](https://www.youtube.com/watch?v=6vqg9cAkMbY), [4](https://www.youtube.com/watch?v=5yOLajFFMHE), [5](https://www.youtube.com/watch?v=P5DDvsSF4Wk).

## <a name="roles"></a>Roles
Un rol define el conjunto de permisos concedidos a los usuarios que están asignados a ese rol.
Puede usar tanto los roles integrados como roles personalizados. Los roles integrados abarcan algunos escenarios comunes de Intune. También puede [crear sus propios roles personalizados](create-custom-role.md) con el conjunto de permisos que exactamente necesita. Varios roles de Azure Active Directory tienen permisos para Intune.
Para ver un rol, seleccione **Intune** > **Roles** > **Todos los roles** > elija un rol. Verá las páginas siguientes:

- **Propiedades**: nombre, descripción, tipo, asignaciones y etiquetas de ámbito del rol. 
- **Permisos**: enumera un largo conjunto de conmutadores que definen qué permisos tiene el rol.
- **Asignaciones**: lista de [asignaciones de roles]( assign-role.md) que definen qué usuarios tienen acceso a qué usuarios o dispositivos. Un rol puede tener varias asignaciones y un usuario puede tener varias asignaciones.

### <a name="built-in-roles"></a>Roles integrados
Puede asignar roles integrados a los grupos sin ninguna configuración adicional. No se puede eliminar o editar el nombre, la descripción, el tipo o los permisos de un rol integrado.

- **Operador del departamento de soporte técnico**: realiza tareas remotas relacionadas con usuarios y dispositivos y puede asignar aplicaciones o directivas a usuarios o dispositivos.
- **Administrador de directivas y perfiles**: administra la directiva de cumplimiento, los perfiles de configuración, la inscripción de Apple, los identificadores de dispositivos corporativos y las líneas base de seguridad.
- **Operador de solo lectura**: ve información sobre usuarios, dispositivos, inscripciones, configuraciones y aplicaciones. No puede realizar cambios en Intune.
- **Administrador de aplicaciones**: permite administrar las aplicaciones móviles y administradas, leer la información del dispositivo y ver los perfiles de configuración del dispositivo.
- **Administrador de roles de Intune**: permite administrar los roles de Intune personalizados y agregar las asignaciones de roles de Intune integrados. Esta es la única función de Intune que permite asignar permisos a los administradores.
- **Administrador de la escuela**: administra dispositivos Windows 10 en [Intune for Education](introduction-intune-education.md).
- **Administrador de seguridad de puntos de conexión**: administra las características de seguridad y cumplimiento, como las líneas de base de seguridad, el cumplimiento de dispositivos, el acceso condicional y ATP de Microsoft Defender.

### <a name="custom-roles"></a>Roles personalizados
Puede crear sus propios roles con permisos personalizados. Para obtener más información sobre los roles personalizados, vea [Creación de un rol personalizado](create-custom-role.md).

### <a name="azure-active-directory-roles-with-intune-access"></a>Roles de Azure Active Directory con acceso a Intune
| Rol de Azure Active Directory | Todos los datos de Intune | Datos de auditoría de Intune |
| --- | :---: | :---: |
| Administrador global | Lectura/escritura | Lectura/escritura |
| Administrador de servicios de Intune | Lectura/escritura | Lectura/escritura |
| Administrador de acceso condicional | None | None |
| Administrador de seguridad | Solo lectura (permisos administrativos completos para el nodo Seguridad de puntos de conexión) | Solo lectura |
| Operador de seguridad | Solo lectura | Solo lectura |
| Lector de seguridad | Solo lectura | Solo lectura |
| Administrador de cumplimiento | Ninguno | Solo lectura |
| Administrador de datos de cumplimiento | Ninguno | Solo lectura |
| Lector global | Solo lectura | Solo lectura |

> [!TIP]
> Intune también muestra tres extensiones de Azure AD: **Usuarios**, **Grupos** y **Acceso condicional**, que se controlan mediante RBAC en Azure AD. Además, el **administrador de cuentas de usuario** solo realiza actividades de usuario o grupo de AAD y no tiene permisos completos para realizar todas las actividades en Intune. Para más información, vea [RBAC con Azure AD](/azure/active-directory/active-directory-assign-admin-roles).

## <a name="role-assignments"></a>Asignaciones de roles
Una asignación de roles define:

- Qué usuarios están asignados al rol.
- Qué recursos pueden ver.
- Qué recursos pueden cambiar.

Puede asignar a los usuarios tanto roles personalizados como integrados. Para asignar un rol de Intune a un usuario, este debe tener una licencia de Intune.
Para ver una asignación de roles, seleccione **Intune** > **Roles** > **Todos los roles** > elija un rol > elija una asignación. Verá las páginas siguientes:

- **Propiedades**: nombre, descripción, rol, miembros, ámbitos y etiquetas de la asignación.
- **Miembros**: todos los usuarios de los grupos de seguridad de Azure mostrados tienen permiso para administrar los usuarios o los dispositivos que aparecen en Ámbito (grupos).
- **Ámbito (grupos)** : los usuarios de Miembros pueden administrar todos los usuarios o dispositivos de estos grupos de seguridad de Azure.
- **[Ámbito (etiquetas)](scope-tags.md)** : los usuarios de Miembros pueden ver los recursos que tienen las mismas etiquetas de ámbito.

### <a name="multiple-role-assignments"></a>Asignaciones de varios roles
Si un usuario tiene varias asignaciones de roles, los permisos y las etiquetas de ámbito de estas asignaciones de roles se amplían a diferentes objetos, como se indica a continuación:

- Los permisos de asignación y las etiquetas de ámbito solo se aplican a los objetos (como directivas o aplicaciones) del Ámbito (grupos) de la asignación de ese rol. Los permisos de asignación y las etiquetas de ámbito no se aplican a los objetos de otras asignaciones de roles, a menos que la otra asignación los conceda específicamente.
- Otros permisos (por ejemplo, los de creación, lectura, actualización y eliminación) y las etiquetas de ámbito se aplican a todos los objetos del mismo tipo (como todas las directivas o aplicaciones) en cualquiera de las asignaciones del usuario.
- Los permisos y las etiquetas de ámbito para objetos de tipos diferentes (como directivas o aplicaciones) no se aplican entre sí. Por ejemplo, un permiso de lectura para una directiva no proporciona un permiso de lectura a las aplicaciones de las asignaciones del usuario.

## <a name="next-steps"></a>Pasos siguientes
- [Asignar de un rol a un usuario](assign-role.md)
- [Crear un rol personalizado](create-custom-role.md)