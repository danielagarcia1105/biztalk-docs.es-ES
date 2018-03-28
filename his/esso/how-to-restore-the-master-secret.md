---
title: Cómo restaurar el secreto principal | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b331c9c5-ca90-4a05-b3f6-59db88bf73dc
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5e640f2762ed9f9cc03a7795062c98a6aa76a59d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-restore-the-master-secret"></a>Cómo restaurar el secreto principal
Como parte de los procedimientos de recuperación de datos, es posible que deba restaurar el secreto principal para poder reutilizar los datos existentes. Para llevar a cabo esta tarea, debe iniciar sesión en el servidor secreto principal mediante el uso de una cuenta que sea un administrador de Windows y un administrador de inicio de sesión único (SSO).  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a>Para restaurar el secreto principal mediante el Complemento MMC  
  
1.  Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento de Microsoft Management Console (MMC) de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **System**y, a continuación, haga clic en **restaurar secreto principal**.  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a>Para restaurar el secreto principal utilizando la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **programas**y, a continuación, haga clic en **Accesorios**. Haga clic en **símbolo**y, a continuación, haga clic en **ejecutar como...** .  
  
2.  Seleccione el administrador apropiado y, a continuación, haga clic en **Aceptar**.  
  
3.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de `ssoconfig –restoresecret <restore file>`, donde  *\<Restaurar archivo >* es la ruta de acceso y nombre del archivo donde se almacena el secreto principal.  
  
## <a name="see-also"></a>Vea también  
 [Cómo generar el secreto principal](../esso/how-to-generate-the-master-secret.md)   
 [Cómo realizar copias de seguridad del secreto principal](../esso/how-to-back-up-the-master-secret.md)   
 [Servidor secreto principal](../esso/master-secret-server.md)   
 [Administración del secreto maestro](../esso/managing-the-master-secret.md)