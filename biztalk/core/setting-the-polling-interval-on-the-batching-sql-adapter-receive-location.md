---
title: "Establecer el intervalo de sondeo en el adaptador SQL por lotes de ubicación de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- polling interval [receive adapters]
- SQL adapters, polling interval
- receive locations, polling interval
- SQL adapters, receive locations
- receive locations, SQL adapters
ms.assetid: 9053b20d-145a-4445-b414-c0482cf975a0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 830cafc89c87ce84048bad8f6e4e9f2feb34f565
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a>Definir el intervalo de sondeo en la ubicación de recepción del adaptador de SQL de procesamiento por lotes
Puede establecer el intervalo de sondeo en el procesamiento por lotes de recepción del adaptador SQL ubicación (**BatchControlMessageRecvLoc**) diferente en los equipos de desarrollo y producción. En un servidor de desarrollo, Microsoft recomienda que mantenga el intervalo de sondeo en el valor predeterminado de 30 segundos para una rápida activación de la orquestación de procesamiento por lotes de un acuerdo. Sin embargo, en un servidor de producción, un valor de 30 segundos puede afectar al rendimiento. Una vez activado un lote, puede que desee definir el intervalo de sondeo a un valor mayor, como cinco minutos.  
  
 Para obtener más información acerca de las entidades, consulte [administrar entidades](../core/managing-parties.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-set-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a>Para definir el intervalo de sondeo en la ubicación de recepción del adaptador de SQL de procesamiento por lotes  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **aplicación EDI de BizTalk**y, a continuación, haga clic en **ubicaciones de recepción**. Haga clic en **BatchControlMessageRecvLoc**y haga clic en **propiedades**.  
  
2.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **transporte** sección, haga clic en **configurar**.  
  
3.  En el **propiedades de transporte SQL** diálogo cuadro, cambie el valor de **intervalo de sondeo** desde el valor predeterminado de "30" en el valor deseado. El valor recomendado para el servidor de producción es "5".  
  
4.  Cambie el valor de **unidad de sondeo de medida** desde el valor predeterminado de **segundos** a **minutos**.  
  
5.  Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo  
  
## <a name="see-also"></a>Vea también  
 [Administrar soluciones EDI y AS2](../core/managing-edi-and-as2-solutions.md)