---
title: Configurar manualmente un enlace de puerto físico para el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, sending messages to the SAP system
- physical port binding, manually configuring
- deploying, receiving messages from the SAP system
ms.assetid: c4f547aa-5514-4ca9-809b-d8d395de419c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 725a26eed4502e0a3d1eca8ed5f1429988590614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216588"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sap-adapter"></a>Configurar manualmente un enlace de puerto físico para el adaptador SAP
Configurar la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como un enlace personalizado de WCF mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. 

## <a name="port-overview"></a>Información general de puerto
Después de implementar el adaptador, podrá enviar y recibir mensajes desde el sistema SAP mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Los pasos para implementar el adaptador varían en función de:  
  
-   La dirección de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Puede optar por configurar un envío, recepción, envío y recepción o un puerto de envío de recepción. Las opciones disponibles se resumen en la siguiente tabla:  
  
    |Dirección de puerto|Patrón de comunicación|Dirección de comunicación para elegir|  
    |---|---|---|  
    |Send|Unidireccional|Siempre enviaré los mensajes en este puerto.|  
    |Receive|Unidireccional|Siempre recibiré los mensajes en este puerto.|  
    |Envío-Recepción|Solicitud-respuesta|Enviar una solicitud y recibiré una respuesta.|  
    |Recepción-Envío|Petición-respuesta|Recibiré una solicitud y enviaré una respuesta.|  
  
     Para obtener más información, consulte [crear un puerto de envío](../../core/how-to-create-a-send-port2.md), o [crear un puerto de recepción](../../core/how-to-create-a-receive-port.md).
  
-   Si el adaptador envía mensajes al sistema SAP o recibe mensajes desde el sistema SAP. Dependiendo de si desea enviar o recibir mensajes, se crea un envío o puerto de recepción.  
  
    > [!NOTE]
    >  También puede configurar el envío o puertos de recepción mediante la importación de un archivo de configuración de enlace que se crea mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] como parte de la generación de metadatos. Para obtener instrucciones acerca de cómo configurar los puertos que utilizan este archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar un puerto mediante el adaptador WCF-custom y el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter.md)  
  
-   [Configurar un puerto con un adaptador SAP de WCF](../../adapters-and-accelerators/adapter-sap/configure-a-port-using-the-wcf-sap-adapter.md)  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)