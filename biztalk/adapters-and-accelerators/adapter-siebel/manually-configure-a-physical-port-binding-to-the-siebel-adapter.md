---
title: Configurar manualmente un enlace de puerto físico para el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- physical port binding, manually configuring
- how to, manually configure adapters for sending messages to a Siebel system
ms.assetid: a1445b8a-440f-45e8-96e9-a13142ca87c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed94ca9f6a44919684d36a1be931cbb33f746377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222124"
---
# <a name="manually-configure-a-physical-port-binding-to-the-siebel-adapter"></a>Configurar manualmente un enlace de puerto físico para el adaptador de Siebel
Esta sección proporciona información acerca de cómo configurar el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] como un enlace personalizado de WCF mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Después de implementar el adaptador, podrá enviar y recibir mensajes desde el sistema Siebel utilizando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Los pasos para implementar el adaptador varían en función de la dirección de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Puede configurar un envío o un puerto de envío y recepción. Las opciones disponibles se resumen en la siguiente tabla:  
  
|Dirección de puerto|Patrón de comunicación|Dirección de comunicación para elegir|  
|---|---|---|  
|Send|Unidireccional|Siempre enviaré los mensajes en este puerto.|  
|Envío-Recepción|Solicitud-respuesta|Enviar una solicitud y recibiré una respuesta.|  
  
 Para obtener más información, consulte [crear y configurar puertos de envío](../../core/creating-and-configuring-send-ports.md).
  
> [!NOTE]
>  Recepción puertos no se admiten porque el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no habilita las operaciones de entrada en el sistema Siebel.  
  
> [!NOTE]
>  También puede configurar los puertos de envío WCF-Custom mediante la importación de un archivo de configuración de enlace que se crea mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] como parte de la generación de metadatos. Para obtener instrucciones acerca de cómo configurar los puertos que utilizan este archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).
  
 
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)