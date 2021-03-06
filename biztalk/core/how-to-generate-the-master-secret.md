---
title: Cómo generar el secreto principal | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, generating
- managing [Master Secret server], generating
ms.assetid: 5512a8ee-bc5b-4fe4-90c7-41e3baaa723b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41e7f000dbb53a054259ba18f5c1d118531c8138
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978341"
---
# <a name="how-to-generate-the-master-secret"></a>Cómo generar el secreto principal
Debe tener derechos de administrador en el servidor secreto principal para realizar esta tarea. Asimismo, debe realizar esta tarea en el servidor secreto principal.  
  
 El primer servidor en el que instala el inicio de sesión único empresarial se convierte en el servidor secreto principal.  
  
> [!IMPORTANT]
>  Sólo puede haber un servidor secreto principal en el sistema SSO.  
> 
> [!NOTE]
>  Cuando se instala el inicio de sesión único empresarial como parte de la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el secreto principal se genera como parte del Asistente para configuración. Sólo necesita realizar esta tarea si desea generar un secreto principal nuevo.  
  
### <a name="to-generate-the-master-secret-using-the-mmc-snap-in"></a>Para generar el secreto principal mediante el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **sistema**y, a continuación, haga clic en **generar secreto**.  
  
### <a name="to-generate-the-master-secret-using-the-command-line"></a>Para generar el secreto principal mediante la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo **ssoconfig-generateSecret \< *archivo de copia de seguridad*\>**, donde \< *archivo de copia de seguridad* \> es el nombre de la archivo que contiene el secreto principal.  
  
     Se le pedirá que escriba una contraseña para proteger el archivo que acaba de crear.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo realizar copias de seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md)   
 [Servidor secreto principal](../core/master-secret-server.md)   
 [Administración del secreto maestro](../core/managing-the-master-secret.md)