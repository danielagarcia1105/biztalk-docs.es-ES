---
title: "Cómo restaurar el secreto principal | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], restoring
- Master Secret server, restoring
- restoring, Master Secret server
ms.assetid: 68e133c5-4591-4d76-9a3b-c9564ff1aa60
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2550d8e1ea0ad45147b2f27daef7244f6c18770b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-restore-the-master-secret"></a>Cómo restaurar el secreto principal
Como parte de los procedimientos de recuperación de datos, es probable que tenga que restaurar el secreto principal para poder reutilizar los datos existentes. Para realizar esta tarea, debe iniciar la sesión en el servidor secreto principal con una cuenta que sea administrador de Windows y administrador de SSO.  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a>Para restaurar el secreto principal mediante el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **System**y, a continuación, haga clic en **restaurar secreto**.  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a>Para restaurar el secreto principal utilizando la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**y, a continuación, haga clic en **Accesorios**. Haga clic en **símbolo**y, a continuación, haga clic en **ejecutar como...** .  
  
2.  Seleccione el administrador apropiado y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssoconfig – restoreSecret \<Restaurar archivo >**, donde  **\<Restaurar archivo >** es la ruta de acceso y nombre del archivo donde se almacena el secreto principal.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)   
 [Cómo realizar copias de seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md)   
 [Servidor secreto principal](../core/master-secret-server.md)   
 [Administrar el secreto principal](../core/managing-the-master-secret.md)