---
title: "Degradación de MSMQT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e7095c73cd337a1fb08f2d867e817ad5838206
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="msmqt-deprecation"></a>Degradación de MSMQT
La característica MSMQT se ha quitado de BizTalk Server. En el Diseñador de orquestaciones, la opción de transporte MSMQT sigue estando disponible en el Asistente para configuración de puertos de tiempo de diseño, tal como se muestra en la imagen siguiente cuando elige la **especificar ahora** opción **deenlacedepuerto**.  
  
 **Asistente para configuración de puertos que muestra el transporte MSMQT**  
  
 ![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")  
  
## <a name="biztalk-server-projects"></a>Proyectos de BizTalk Server  
 Los nuevos proyectos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no deben utilizar la opción de transporte MSMQT. Implementación de aplicación en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se producirá un error con el error **tipo de protocolo "MSMQT" no se encuentra**.  
  
## <a name="migrated-biztalk-server-projects"></a>Proyectos migrados de BizTalk Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]los proyectos se pueden migrar a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] mediante el uso de la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Asistente de conversión, como se documenta en [migrar un proyecto de BizTalk Server](../core/migrating-a-biztalk-server-project.md). Los proyectos que contienen puertos configurados para usar el transporte MSMQT deben reconfigurarse manualmente antes de su implementación en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]. La reconfiguración recomendada es usar el adaptador de MSMQ.  Para obtener más información acerca del adaptador MSMQ vea [¿qué es el adaptador de MSMQ?](../core/what-is-the-msmq-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Migrar desde el adaptador de MSMQT al adaptador de MSMQ](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)