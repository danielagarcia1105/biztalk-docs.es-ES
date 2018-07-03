---
title: Creación de Roles y departamentos para reparación de mensajes y nuevo envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21abbaa8b5e3b36dfb5ad9091afa0e05a6d807d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988885"
---
# <a name="creating-departments-and-roles-for-message-repair-and-new-submission"></a>Creación de Roles y departamentos para reparación de mensajes y nuevo envío
Reparación de mensajes y nuevo envío implica las siguientes cuatro operaciones diferentes:  
  
- Reparación de un mensaje que no se pudo validar  
  
- Comprobación de la reparación (incluida la regeneración de claves)  
  
- Aprobación de la reparación  
  
- Creación de un nuevo mensaje  
  
  Para llevar a cabo una de estas operaciones, un usuario debe asumir el rol asociado a la operación. La función también debe formar parte del departamento de procesamiento (que se describe a continuación). Para enviar el mensaje después de realizar una fase en el flujo de trabajo, el usuario debe firmar el mensaje con un certificado válido asociado al usuario.  
  
## <a name="creating-departments-and-roles"></a>Creación de Roles y departamentos  
 Consulte la documentación del cliente Web de perfil.  
  
## <a name="rules-of-role-use"></a>Reglas de uso de roles  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] los usuarios, roles y los departamentos de TI deben cumplir las reglas siguientes:  
  
- El flujo de trabajo completo para un mensaje reparado es reparar, comprobar y, a continuación, aprobar el mensaje. El flujo de trabajo completo para un mensaje creado es reparar, crear, comprobar y, a continuación, aprobar el mensaje. Los pasos de comprobación y aprobación son opcionales.  
  
- Flujo de trabajo de un departamento debe comenzar con un rol de creación o reparación. Si un flujo de trabajo incluye pasos de creación y reparación (un flujo de trabajo para un mensaje creado), el paso crear debe aparecer inmediatamente antes del paso de reparación.  
  
- Puede contener uno y solo un rol que tiene una capacidad de crear un flujo de trabajo para un mensaje creado.  
  
- Cada flujo de trabajo debe contener uno y solo un rol que tenga una funcionalidad de reparación.  
  
- Un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario puede asociarse con más de un rol, pero ningún usuario puede ejecutar más de un paso en un único flujo de trabajo. Por ejemplo, si el usuario A repara un mensaje y el usuario B comprueba el mensaje, a continuación, ni un usuario ni el usuario B puede aprobar el mensaje.  
  
- No hay ninguna comprobación del orden de los roles con la capacidad del RekeyVerify o aprobar en relación con otras funciones con capacidad de RekeyVerify o aprobar.  
  
- Si un mensaje que ya ha reparado se produce un error de validación de nuevo, vuelve a la Bandeja de entrada de reparación en la biblioteca de documentos del sitio MRSR. Cuando esto sucede, ya no se aplican las limitaciones anteriores en las funciones de comprobación y aprobador (según quién ya ha realizado un rol en el flujo de trabajo). Por ejemplo, si las reparaciones de usuario A un mensaje, el usuario B rechaza el mensaje en la comprobación y reparación de un usuario el mensaje una segunda vez, a continuación, un usuario que no sea el usuario B puede comprobar el mensaje. Si es así, el usuario B podría aprobar el mensaje. Otro ejemplo es que si un usuario crea un mensaje, el usuario B rechaza el mensaje de comprobación y usuario C repara el mensaje, a continuación, el usuario A podría comprobar el mensaje.  
  
- Un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario que crea un mensaje también puede reparar dicho mensaje si se produce un error de validación.  
  
- Sólo [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] los usuarios del departamento asociado con un flujo de trabajo pueden realizar un paso del flujo de trabajo. Cuando un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario envía un mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] comprueba que el usuario tiene un rol en el departamento asociado con el mensaje (a través del usuario perfiles (en caso de que el departamento no es el valor predeterminado) en el cliente web de perfil).  
  
- Un administrador puede ofrecer una sola [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario varios roles dentro de un departamento. Un único usuario puede realizar la reparación, comprobación o creación, aprobación o cualquier subconjunto de esos roles, sujeto a las limitaciones en cualquier flujo de trabajo que se ha descrito anteriormente.  
  
## <a name="certificates"></a>Certificados  
 Para enviar un mensaje en el equipo local después de reparar, comprobación, aprobación o creación, la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario debe firmar el mensaje con su certificado. Para obtener más información sobre cómo crear certificados, consulte [instalar certificados](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md).  
  
 Para que pueda reparar, comprobar, aprobar o crear un mensaje de acceso al sitio de MRSR desde un equipo cliente remoto, el usuario debe agregar su certificado en los certificados - usuario actual/Personal/certificados almacén de su equipo cliente (el usuario no tiene para ser un administrador que lo haga). Además, un administrador en el servidor debe agregar el certificado del usuario (y las de otros usuarios que acceden al servidor desde el equipo cliente) a los certificados (equipo Local) / almacén otras personas/certificados en el servidor.  
  
 Un único usuario podría tener varios roles asignadas y debe usar el mismo certificado al realizar cualquiera de esos roles.