---
title: "Cómo realizar copias de seguridad del Portal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cea02e6-e387-4048-a1f3-d7c3c562f470
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e7308e54505c795e35ffa2fbb2d287c1a49ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-the-bam-portal"></a>Cómo realizar una copia de seguridad del portal de SAE
Si utiliza Supervisión de la actividad económica (SAE), debe realizar una copia de seguridad del portal de SAE como parte de la realización de copias de seguridad de su servidor de BizTalk Server. Si no utiliza SAE, este procedimiento es opcional.  
  
 Algunas partes del proceso de copia de seguridad difieren en gran medida en función de la versión de Internet Information Services (IIS) de la que esté realizando una copia de seguridad. IIS 6.0 permite realizar una copia de seguridad de la configuración del grupo de aplicaciones y de la configuración de sitio web de manera independiente; también puede cifrar los archivos de copia de seguridad de la configuración mediante una contraseña.  
  
 IIS 7.0 guarda la configuración para el sitio web y el grupo de aplicaciones en un único archivo applicationHost.config. No se cifra el archivo applicationHost.config, pero las contraseñas de cuenta, si los hay, se cifran en el archivo. El cifrado se realiza mediante el certificado del equipo del que está realizando una copia de seguridad. Esta configuración no se puede restaurar en un equipo distinto de aquel en el que se originó.  
  
 No se puede realizar copias de seguridad de la configuración de portal de BAM mediante el Administrador de IIS 7.0; debe utilizar el **Appcmd.exe** herramienta de línea de comandos. Para obtener más información acerca de Appcmd, vea [http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.  
  
### <a name="to-back-up-the-bam-portal-iis-70"></a>Para realizar una copia de seguridad del portal de BAM (IIS 7.0)  
  
1.  Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**.  
  
2.  En el cuadro de diálogo Ejecutar, en el cuadro Abrir, escriba lo siguiente: `runas /user:` *computername*`\`*accountname* `cmd`y, a continuación, haga clic en **Aceptar** o Presione **ENTRAR**.  
  
     *AccountName* debe ser miembro del grupo Administradores en el equipo local.  
  
3.  Cuando se le solicite, escriba la contraseña de *accountname*y, a continuación, presione **ENTRAR**.  
  
4.  Tipo de `cd %windir%\system32\inetsrv`y, a continuación, presione **ENTRAR**.  
  
5.  Tipo de `appcmd add backup “` *nombrecopiadeseguridad*`”`y, a continuación, presione **ENTRAR**.  
  
     No es necesario que escriba un nombre para la copia de seguridad. Si no se indica, se generará automáticamente. Un ejemplo de nombre de la copia de seguridad generado automáticamente es “20090224T123302”.  
  
     Para ver una lista de copias de seguridad de configuración existente, escriba `appcmd list backup`y, a continuación, presione **ENTRAR**. Copias de seguridad creadas por el usuario se guardan en el **%windir%\system32\inetsrv\backup** directory. Para ver una lista de las opciones de copia de seguridad proporcionadas por **appcmd.exe**, tipo `appcmd backup /?`y, a continuación, presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Realizar una copia de seguridad de un equipo que ejecuta BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md)   
 [Recuperar un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)   
 [Portal de BAM](../core/bam-portal.md)