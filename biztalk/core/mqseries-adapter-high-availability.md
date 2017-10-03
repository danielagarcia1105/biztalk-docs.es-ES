---
title: Alta disponibilidad del adaptador de MQSeries | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, MQSeries adapters
- MQSeries adapters, availability
- MQSeries adapters, performance
- high availability, MQSeries adapters
ms.assetid: 4339b10b-b35d-47c0-b78a-c60207e06c8e
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c0b6486e49cb2ccddfab37271a94a4ba7a6948
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-high-availability"></a>Alta disponibilidad del adaptador de MQSeries
Puede mejorar la disponibilidad de las siguientes formas al usar el adaptador:  
  
-   Configure un entorno de host de tolerancia a errores para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Utilice la organización por clústeres de Windows con IBM WebSphere MQ.  
  
 Para obtener información acerca de la tolerancia a errores y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md) y [planeación de la plataforma para tolerancia a errores](../core/planning-your-platform-for-fault-tolerance.md) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 Para asegurarse de que el adaptador de MQSeries para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es capaz de comunicarse con una instalación remota del componente MQSAgent, asegúrese de que ha habilitado el acceso de red COM+ en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y en el servidor en el que está instalado IBM WebSphere MQ. Para obtener más información acerca de cómo habilitar el acceso de red COM +, consulte Microsoft Knowledge Base el artículo 817065, "Cómo habilitar el acceso de red COM + en Windows Server 2003," disponible en [http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580).  
  
 No es necesario organizar por clústeres la aplicación MQSAgent (MQSAgent2) COM+ que se utiliza con el adaptador de MQSeries para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para proporcionar una alta disponibilidad a este componente, instale el componente en cada nodo de clúster. Si detiene la aplicación COM+, la siguiente llamada del cliente la reiniciará.  
  
## <a name="see-also"></a>Vea también  
 [Uso del adaptador de MQSeries](../core/using-the-mqseries-adapter.md)