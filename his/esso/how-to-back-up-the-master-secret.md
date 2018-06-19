---
title: Cómo realizar copias de seguridad del secreto principal | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0841c52a-7b15-45f8-9900-f5c9e3abd90b
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 124c077d7a15a4938f94239518ad02c8268074a4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30251000"
---
# <a name="how-to-back-up-the-master-secret"></a>Cómo realizar copias de seguridad del secreto principal
Es posible hacer una copia de seguridad del secreto principal desde el servidor secreto principal en un sistema de archivos NTFS o en un medio extraíble, como un disco.  
  
 Debe ser un administrador de inicio de sesión único y un administrador de Windows para realizar esta tarea. El sistema de inicio de sesión único (SSO) le pedirá una contraseña. Para restaurar el secreto posteriormente, debe especificar la misma contraseña.  
  
> [!CAUTION]
>  Si el servidor secreto principal se bloquea y se pierde la clave, o si se daña la clave, no podrá recuperar los datos almacenados en la base de datos de credenciales. Debe hacer copia de seguridad del secreto principal o se arriesga a perder los datos de la base de datos de credenciales.  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a>Para hacer una copia de seguridad del secreto principal utilizando el Complemento MMC  
  
1.  Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento de Microsoft Management Console (MMC) de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **System**y, a continuación, haga clic en **copia de seguridad secreto principal**.  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a>Para hacer una copia de seguridad del secreto principal utilizando la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **programas**y, a continuación, haga clic en **Accesorios**. Haga clic en **símbolo**y, a continuación, haga clic en **ejecutar como...** .  
  
2.  Seleccione el administrador apropiado y, a continuación, haga clic en **Aceptar**.  
  
3.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de `ssoconfig –backupsecret <backup file>`, donde  *\<archivo de copia de seguridad >* es la ruta de acceso y nombre del archivo donde el secreto principal se copiarán, por ejemplo, `A:\ssobackup.bak`.  
  
5.  Proporcione una contraseña para ayudar a proteger este archivo.  
  
     Se le solicitará que confirme la contraseña y que proporcione una sugerencia de contraseña para ayudar a recordar esta última.  
  
> [!IMPORTANT]
>  El archivo de copia de seguridad debe guardarse y almacenarse en una ubicación segura.  
  
## <a name="see-also"></a>Vea también  
 [Cómo generar el secreto principal](../esso/how-to-generate-the-master-secret.md)   
 [Cómo restaurar el secreto principal](../esso/how-to-restore-the-master-secret.md)   
 [Servidor secreto principal](../esso/master-secret-server.md)   
 [Administración del secreto maestro](../esso/managing-the-master-secret.md)