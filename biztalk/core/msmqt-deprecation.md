---
title: Degradación de MSMQT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f869dde7cb4c793e1e36beee6a20bc89d19272e8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007637"
---
# <a name="msmqt-deprecation"></a>Degradación de MSMQT
La característica MSMQT se ha quitado de BizTalk Server. En el Diseñador de orquestaciones, la opción de transporte MSMQT sigue estando disponible en el Asistente para configuración de puertos de tiempo de diseño, tal como se muestra en la imagen siguiente cuando elige la **especificar ahora** opción **deenlacedepuerto**.  
  
 **Asistente para configuración de puertos que muestra el transporte MSMQT**  
  
 ![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")  
  
## <a name="biztalk-server-projects"></a>Proyectos de BizTalk Server  
 Los nuevos proyectos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no deben utilizar la opción de transporte MSMQT. Se producirá un error de implementación de aplicación en el servidor BizTalk Server con el error **tipo de protocolo "MSMQT" no se encuentra**.  
  
## <a name="migrated-biztalk-server-projects"></a>Proyectos migrados de BizTalk Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]los proyectos se pueden migrar a BizTalk Server mediante el uso de la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Asistente de conversión, como se documenta en [migrar un proyecto de BizTalk Server](../core/migrating-a-biztalk-server-project.md). Los proyectos que contienen puertos configurados para usar el transporte MSMQT deben reconfigurarse manualmente antes de la implementación a BizTalk Server. La reconfiguración recomendada es usar el adaptador de MSMQ.  Para obtener más información acerca del adaptador MSMQ vea [¿qué es el adaptador de MSMQ?](../core/what-is-the-msmq-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Migración del adaptador de MSMQT al adaptador de MSMQ](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)