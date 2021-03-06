---
title: Cómo hacer copia de seguridad del secreto principal | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], backing up
- backing up, Master Secret server
- Master Secret server, backing up
ms.assetid: 22c23f66-b7df-4379-8a9f-065406ba8aa8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec9faad19d695d43476e60e87acbd067d7e66896
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008157"
---
# <a name="how-to-back-up-the-master-secret"></a>Cómo realizar copias de seguridad del secreto principal
Es posible hacer una copia de seguridad del secreto principal desde el servidor secreto principal en un sistema de archivos NTFS o en un medio extraíble, como un disco.  
  
 Es preciso ser un administrador de inicio de sesión único y un administrador de Windows para llevar a cabo esta tarea. El sistema de SSO solicitará una contraseña. Para restaurar el secreto posteriormente, debe especificar la misma contraseña.  
  
> [!CAUTION]
>  Si el servidor secreto principal no funciona y se pierde la clave o se daña, no será posible recuperar los datos almacenados en la base de datos de SSO. Se debe hacer una copia de seguridad del secreto principal o, de lo contrario, existirá el riesgo de perder los datos de la base de datos de SSO.  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a>Para hacer una copia de seguridad del secreto principal utilizando el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **sistema**y, a continuación, haga clic en **secreto de copia de seguridad**.  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a>Para hacer una copia de seguridad del secreto principal utilizando la línea de comandos  
  
1. En el **iniciar** menú, haga clic en **todos los programas**y, a continuación, haga clic en **Accesorios**. Haga clic en **símbolo**y, a continuación, haga clic en **ejecutar como...** .  
  
2. Seleccione el administrador apropiado y, a continuación, haga clic en **Aceptar**.  
  
3. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4. Tipo ** ssoconfig-backupSecret *\<archivo de copia de seguridad\>**<em>, donde *\<archivo de copia de seguridad\></em>  es la ruta de acceso y nombre del archivo donde se copiará el secreto principal. Por ejemplo, A:\ssobackup.bak  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
5. Proporcione una contraseña para proteger el archivo. Se le solicitará que confirme la contraseña y que proporcione una sugerencia de contraseña para ayudar a recordar esta última.  
  
> [!IMPORTANT]
>  El archivo de copia de seguridad debe guardarse y almacenarse en una ubicación segura.  
  
## <a name="see-also"></a>Vea también  
 [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)   
 [Cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md)   
 [Servidor secreto principal](../core/master-secret-server.md)   
 [Administración del secreto maestro](../core/managing-the-master-secret.md)