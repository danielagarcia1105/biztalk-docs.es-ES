---
title: Instalar el Software eventos BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3638d34-f5a8-4ffd-99eb-d38aed4c0732
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c41606f6056dcc4edb90b4db5ef6a41901835b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-bam-eventing-software"></a>Instalar el software de eventos BAM
Para implementar soluciones de BAM mediante la API de eventos BAM o configurar la aplicación de Windows Workflow Foundation o Windows Communication Foundation para utilizar el interceptor de BAM para Windows Workflow Foundation, debe instalar el software eventos BAM mediante el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] programa de instalación. Este software puede instalarse como parte de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución o por separado seleccionando compatibilidad de eventos de BAM en Software adicional en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] la instalación de aplicación.  
  
### <a name="to-install-the-bam-eventing-software"></a>Para instalar el software de eventos BAM  
  
1.  Inicie sesión en el equipo que alojará la aplicación WF usando una cuenta con privilegios de administrador.  
  
2.  Ejecutar el programa de instalación en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] CD de instalación.  
  
3.  Borre todas las opciones seleccionadas. Si no lleva a cabo este paso, es posible que instale software que no necesita.  
  
4.  Expanda **Software adicional**y, a continuación, seleccione la **eventos BAM** casilla de verificación.  
  
5.  Haga clic en **Siguiente**.  
  
6.  Haga clic en **Instalar**.  
  
7.  Una vez completado el procedimiento de instalación, haga clic en **Aceptar**.  
  
     Así habrá instalado el software de eventos BAM.  
  
> [!NOTE]
>  La instalación de la biblioteca de interceptores de BAM mediante este método no requiere la adquisición de licencias adicionales.  
  
 Si está interesado en supervisar los datos del contador de rendimiento de los interceptores de BAM, en primer lugar deberá registrarlos mediante InstallUtil.exe.  
  
### <a name="to-register-bam-interceptor-performance-counters-by-using-installutilexe"></a>Para registrar los contadores de rendimiento del interceptor de BAM mediante InstallUtil.exe  
  
1.  Iniciar  **[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo** como administrador.  
  
2.  En el símbolo del sistema, escriba el siguiente comando:  
  
     InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll  
  
3.  Tipo de **Exit**, y, a continuación, presione ENTRAR para cerrar el símbolo del sistema.  
  
     A partir de entonces estarán disponibles los contadores de rendimiento del interceptor de BAM.  
  
> [!NOTE]
>  De manera predeterminada, sólo los administradores y algunas cuentas del sistema tienen permiso para registrar datos de rendimiento. Para habilitar el acceso a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], agregue la cuenta usada para ejecutar aplicaciones de flujo de trabajo al grupo usuarios del registro de rendimiento.  
  
## <a name="see-also"></a>Vea también  
 [Implementar soluciones de BAM](../core/implementing-bam-solutions.md)   
 [Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)