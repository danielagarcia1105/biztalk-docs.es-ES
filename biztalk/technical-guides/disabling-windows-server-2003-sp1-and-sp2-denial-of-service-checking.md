---
title: Deshabilitación de Windows Server 2003 SP1 y SP2 denegación de servicio de comprobación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8822c1e4-d146-4361-b25a-7b81cd5cdd3b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 688ff81133e60d5be5ef2f9d6826b9b6ca93919c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979269"
---
# <a name="disabling-windows-server-2003-sp1-and-sp2-denial-of-service-checking"></a>Deshabilitación de Windows Server 2003 SP1 y SP2 denegación de servicio de comprobación
> [!NOTE]  
>  En este tema es aplicable sólo a Windows Server 2003.  
  
 Debe deshabilitar la denegación de Windows Server 2003 Service Pack 1 y Service Pack 2 de la comprobación del servicio. Esto es porque en determinados escenarios de carga alta, Windows Server 2003 SP1 y SP2 denegación de servicio comprobando incorrectamente puede identificar conexiones TCP/IP válidas como un ataque de denegación de servicio.  
  
> [!IMPORTANT]  
>  Debe deshabilitar esta característica solo en un escenario de intranet cuando esté seguro de que no se verá afectado desde real ataques por denegación de servicio.  
  
## <a name="how-denial-of-service-can-affect-tcpip-connections"></a>Cómo denegación de servicio puede afectar a las conexiones TCP/IP  
 Windows Server 2003 SP1 y SP2 implementan una característica de seguridad que reduce el tamaño de la cola para conexiones simultáneas de TCP/IP con el servidor. Esta característica contribuye a evitar los ataques de denegación de servicio. En condiciones de mucha carga, el protocolo TCP/IP en Windows Server 2003 SP1 o posterior puede identificar incorrectamente conexiones TCP/IP válidas como un ataque de denegación de servicio. Esto puede ocurrir cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está sobrecargado.  
  
## <a name="modifying-the-registry-entry"></a>Modificar la entrada del registro  
 Para obtener más información, consulte el artículo de Microsoft Knowledge Base 899599, ["se produce un error en una instancia de Host de BizTalk Server, y se escribe un error General de red en el registro de aplicación cuando el servidor basado en BizTalk Server procesa un gran volumen de documentos" ](http://go.microsoft.com/fwlink/?LinkId=158860) (<http://go.microsoft.com/fwlink/?LinkId=158860>). Siga las instrucciones de este artículo para crear el **SynAttackProtect** entrada del registro en equipos que ejecutan SQL Server que hospedan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos y en los equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que ejecutan Windows Server 2003 SP1 o posterior.  
  
## <a name="tuning-registry-settings-that-govern-the-level-of-denial-of-service-attack-protection"></a>Ajuste la configuración del registro que controlan el nivel de servicio protección frente a ataques de denegación  
 En ciertos escenarios desea mantener la denegación de protección del servicio pero reducen la agresividad se aplica la denegación de funcionalidad del servicio. Es posible ajustar el comportamiento predeterminado de la denegación de la característica de protección de servicio siguiendo estos pasos:  
  
1.  Asegúrese de que el **SynAttackProtect** entrada del registro se establece en un valor REG_DWORD de **1** tal como se describe en [ http://go.microsoft.com/fwlink/?LinkId=111477 ](http://go.microsoft.com/fwlink/?LinkId=111477).  
  
2.  Configurar la **TcpMaxHalfOpen** entrada de registro como se describe en [ http://go.microsoft.com/fwlink/?LinkId=111478 ](http://go.microsoft.com/fwlink/?LinkId=111478).  
  
3.  Configurar la **TcpMaxHalfOpenRetried** entrada de registro como se describe en [ http://go.microsoft.com/fwlink/?LinkId=111479 ](http://go.microsoft.com/fwlink/?LinkId=111479).  
  
## <a name="see-also"></a>Vea también  
 [Listas de comprobación de preparación operativa](../technical-guides/operational-readiness-checklists.md)