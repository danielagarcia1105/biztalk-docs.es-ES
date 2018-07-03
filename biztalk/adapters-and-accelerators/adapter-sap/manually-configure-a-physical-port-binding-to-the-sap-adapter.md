---
title: Configurar manualmente un enlace de puerto físico para el adaptador de SAP | Microsoft Docs
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
ms.openlocfilehash: 14aea45a1032a2e01e9560d9ab47e85e75506836
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994613"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sap-adapter"></a>Configurar manualmente un enlace de puerto físico para el adaptador de SAP
Configurar la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como un enlace personalizado de WCF mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. 

## <a name="port-overview"></a>Información general de puerto
Después de implementar el adaptador, podrá enviar y recibir mensajes desde el sistema SAP mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Los pasos para implementar el adaptador varían en función de:  
  
- La dirección de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Puede configurar un envío, recepción, envío y recepción o un puerto de envío de recepción. Las opciones disponibles se resumen en la siguiente tabla:  
  
  |Dirección de puerto|Patrón de comunicación|Dirección de comunicación que elegir|  
  |---|---|---|  
  |Send|Unidireccional|Siempre enviaré los mensajes en este puerto.|  
  |Receive|Unidireccional|Siempre recibiré los mensajes en este puerto.|  
  |Envío-Recepción|Solicitud-respuesta|Enviar una solicitud y recibiré una respuesta.|  
  |Recepción-Envío|Petición-respuesta|Recibiré una solicitud y enviaré una respuesta.|  
  
   Para obtener más información, consulte [crear un puerto de envío](../../core/how-to-create-a-send-port2.md), o [crear un puerto de recepción](../../core/how-to-create-a-receive-port.md).
  
- Si el adaptador envía mensajes al sistema SAP o recibe mensajes desde el sistema SAP. Dependiendo de si desea enviar o recibir mensajes, creará un envío o puerto de recepción.  
  
  > [!NOTE]
  >  También puede configurar el envío o los puertos de recepción mediante la importación de un archivo de configuración de enlace que se crea mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] como parte de la generación de metadatos. Para obtener instrucciones sobre cómo configurar los puertos que usa este archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar un puerto mediante el adaptador WCF-custom y el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter.md)  
  
-   [Configurar un puerto mediante el adaptador personalizado de SAP de WCF](../../adapters-and-accelerators/adapter-sap/configure-a-port-using-the-wcf-sap-adapter.md)  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)