---
title: Cómo instalar la sincronización de contraseñas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, Password Synchronization [SSO]
- Password Synchronization [SSO], installing
ms.assetid: 8ace0401-b759-4ea3-91a0-be2aa8b5a5a4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1cd2db294ae0bd9e32db1a81209fe9226512e2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996213"
---
# <a name="how-to-install-password-synchronization"></a>Cómo instalar la sincronización de contraseñas
Al igual que con las demás características de inicio de sesión único, Sincronización de contraseñas no se instala con la instalación predeterminada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], sino que se debe seleccionar de forma específica durante la instalación.  
  
### <a name="to-install-password-synchronization"></a>Para instalar Sincronización de contraseñas  
  
1. En el CD de BizTalk Server, vaya a la  **\<CDRoot\>\Platforms\SSO** carpeta.  
  
2. Ejecute **setup.exe** y siga las instrucciones del asistente.  
  
3. Seleccione el **la sincronización de contraseña** de características y continuar con la instalación.  
  
   Además, se necesitan los adaptadores de sincronización de contraseñas para enviar y recibir cambios de contraseña en el sistema externo. Los temas de esta sección explican cómo configurar sus propios adaptadores.  
  
   También puede ponerse en contacto con los alias de soporte técnico para obtener información acerca de los adaptadores de sincronización de contraseñas disponibles.  
  
   Finalmente, para capturar los cambios de contraseña realizados en Active Directory, además de instalar la característica de sincronización de contraseñas de ENTSSO, es preciso instalar componentes en los controladores de dominio para capturar los cambios de contraseña.  
  
   Tanto Windows Password Capture como Password Change Notification Service (PCNS) deben estar instalados en todos los controladores de dominio de los que se van a capturar contraseñas. Puede instalar estos componentes desde la siguiente ubicación:  
  
   [http://go.microsoft.com/fwlink/?LinkId=68145](http://go.microsoft.com/fwlink/?LinkId=68145)  
  
   Lea la documentación que los acompaña (también en esta carpeta) antes de proceder con la instalación en el controlador de dominio.  
  
## <a name="see-also"></a>Vea también  
 [Sincronización de contraseñas](../core/password-synchronization2.md)