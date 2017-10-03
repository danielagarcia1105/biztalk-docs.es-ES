---
title: "Crear Roles y departamentos de reparación de mensajes y nuevo envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- departments, creating
- creating, roles
- roles, requirements
- roles, creating
- creating, departments
- certificates, messages
- messages, certificates
ms.assetid: 6337bd57-63c5-4d97-b558-ac27d5eb60d7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d033ab3910657373f6e48b1f6e6bed076f730b51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-departments-and-roles-for-message-repair-and-new-submission"></a>Crear Roles y departamentos de reparación de mensajes y nuevo envío
Reparación de mensajes y nuevo envío implica las siguientes cuatro operaciones diferentes:  
  
-   Reparación de un mensaje que no se pudo validar  
  
-   Comprobación de la reparación (incluida la regeneración de claves)  
  
-   Aprobación de la reparación  
  
-   Creación de un nuevo mensaje  
  
 Para llevar a cabo una de estas operaciones, un usuario debe asumir el rol asociado a la operación. La función también debe ser una parte del departamento de procesamiento (que se describe a continuación). Para enviar el mensaje después de llevar a cabo una fase en el flujo de trabajo, el usuario debe firmar el mensaje con un certificado válido asociado al usuario.  
  
## <a name="creating-departments-and-roles"></a>Creación de departamentos y Roles  
 Consulte la documentación del cliente Web de perfil.  
  
## <a name="rules-of-role-use"></a>Reglas de uso de roles  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]los usuarios, roles y departamentos deben cumplir las reglas siguientes:  
  
-   El flujo de trabajo completo para un mensaje reparado es reparar, comprobar y, a continuación, aprobar el mensaje. El flujo de trabajo completo para un mensaje creado consiste en crear, reparar, comprobar y, a continuación, aprobar el mensaje. Los pasos de comprobación y aprobación son opcionales.  
  
-   Flujo de trabajo del departamento debe comenzar con un rol de creación o reparación. Si un flujo de trabajo incluye los pasos de creación y reparar (un flujo de trabajo para un mensaje creado), el paso de creación debe proceder inmediatamente antes del paso de reparación.  
  
-   Un flujo de trabajo para un mensaje creado debe contener un solo rol que tiene una capacidad de crear.  
  
-   Cada flujo de trabajo debe contener un solo rol que tiene una capacidad de reparación.  
  
-   Un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario puede asociarse con más de un rol, pero ningún usuario puede ejecutar más de un paso en un único flujo de trabajo. Por ejemplo, si el usuario A repara un mensaje y el usuario B comprueba el mensaje, a continuación, ni el usuario ni el usuario B puede aprobar el mensaje.  
  
-   No hay ninguna comprobación en el orden de los roles con la capacidad de RekeyVerify o aprobar en relación con otros roles con la capacidad de RekeyVerify o aprobar.  
  
-   Si un mensaje que ya se reparó no puede volver a validar, lo vuelve a la Bandeja de entrada de reparación en la biblioteca de documentos del sitio MRSR. Cuando esto sucede, ya no se aplican las limitaciones anteriores de las funciones de comprobación y aprobador (basadas en un rol ya que ha efectuado en el flujo de trabajo). Por ejemplo, si las reparaciones de usuario A un mensaje, el usuario B rechaza el mensaje en la comprobación y reparaciones de usuario al mensaje una segunda vez, a continuación, un usuario que no sea el usuario B puede comprobar el mensaje. Si es así, el usuario B podría aprobar el mensaje. Otro ejemplo es que si un usuario crea un mensaje, el usuario B rechaza el mensaje de comprobación y usuario C repara el mensaje, a continuación, el usuario A podría comprobar el mensaje.  
  
-   Un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario que crea un mensaje también puede reparar ese mensaje si se produce un error de validación.  
  
-   Sólo [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] los usuarios del departamento asociado con un flujo de trabajo pueden realizar un paso del flujo de trabajo. Cuando un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario envía un mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] comprueba que el usuario tiene un rol en el departamento asociado con el mensaje (a través del usuario perfiles (en caso de que el departamento no es el valor predeterminado) en el cliente web de perfil).  
  
-   Un administrador puede conceder a un único [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario varios roles dentro de un departamento. Un usuario puede realizar la reparación, la comprobación, aprobación, o creación o cualquier subconjunto de esos roles, sujeto a las limitaciones en cualquier un flujo de trabajo que se ha descrito anteriormente.  
  
## <a name="certificates"></a>Certificados  
 Para enviar un mensaje en el equipo local después de la reparación, la comprobación, la aprobación o la creación, la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario debe firmar el mensaje con su certificado. Para obtener más información acerca de cómo crear certificados, consulte [instalar certificados](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md).  
  
 Para que pueda reparar, compruebe, aprobar o crear un mensaje de acceso al sitio MRSR desde un equipo cliente remoto, el usuario debe agregar su certificado en el almacén de usuario actual/Personal/certificados de su equipo cliente (el usuario no tiene los certificados- para ser un administrador para ello). Además, un administrador en el servidor debe agregar el certificado del usuario (y los de otros usuarios que acceden al servidor desde el equipo cliente) a los certificados (equipo Local) / almacén otras personas/certificados en el servidor.  
  
 Un único usuario podría tener varios roles asignadas y debe usar el mismo certificado al realizar cualquiera de esos roles.