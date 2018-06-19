---
title: Configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, sending to an Oracle database
- messages, receiving from an Oracle database
- physical port binding, manually configuring
ms.assetid: 6b118236-e9eb-494e-96b2-969c7064943d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a64223485cf83fb214055cb1e11b44fb6bc7c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214284"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-database-adapter"></a>Configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle
Esta sección proporciona información acerca de cómo configurar el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] como un enlace WCF-Custom o WCF-OracleDB enlace mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Después de implementar el adaptador, podrá enviar y recibir mensajes desde la base de datos de Oracle mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Los pasos para implementar el adaptador varían en función de:  
  
-   La dirección de comunicación entre el servidor BizTalk Server y [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Puede configurar un envío, recepción, envío y recepción o un puerto de envío de recepción. Las opciones se resumen en la tabla siguiente.  
  
    |Dirección de puerto|Patrón de comunicación|Dirección de comunicación para elegir|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |Send|Unidireccional|Siempre enviaré los mensajes en este puerto.|  
    |Receive|Unidireccional|Siempre recibiré los mensajes en este puerto.|  
    |Envío y recepción|Solicitud-respuesta|Enviar una solicitud y recibiré una respuesta.|  
    |Envío de recepción|Petición-respuesta|Recibiré una solicitud y enviaré una respuesta.|  
  
     Para obtener más información, consulte [crear un puerto de envío](../../core/how-to-create-a-send-port2.md), o [crear un puerto de recepción](../../core/how-to-create-a-receive-port.md). 
  
-   Si el adaptador envía mensajes a la base de datos de Oracle o recibe mensajes de la base de datos de Oracle. Dependiendo de si desea enviar o recibir mensajes, se crea un envío o puerto de recepción, respectivamente.  
  
    > [!NOTE]
    >  También puede configurar el envío o puertos de recepción mediante la importación de un archivo de configuración de enlace que se crea mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] como parte de la generación de metadatos. Para obtener instrucciones acerca de cómo configurar los puertos que utilizan este archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
 
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de BizTalk](../../core/develop-your-biztalk-applications.md)