---
title: "Configurar manualmente un enlace de puerto físico para el adaptador de SQL | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f0bb78-c85f-4629-9e2d-cce180ff78ae
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac72d914539eabc9b129985c2b9335270e561d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-sql-adapter"></a>Configurar manualmente un enlace de puerto físico para el adaptador de SQL
Esta sección proporciona información acerca de cómo configurar el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] como un enlace personalizado de WCF o como un puerto de WCF-SQL mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Después de implementar el adaptador, podrá enviar y recibir mensajes de SQL Server mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Los pasos para implementar el adaptador varían en función de:  
  
-   La dirección de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Puede configurar un envío, recepción, o un puerto de envío y recepción. Las opciones se resumen en la tabla siguiente.  
  
    |Dirección de puerto|Patrón de comunicación|Dirección de comunicación para elegir|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |Send|Unidireccional|Siempre enviaré los mensajes en este puerto.|  
    |Receive|Unidireccional|Siempre recibiré los mensajes en este puerto.|  
    |Envío y recepción|Solicitud-respuesta|Enviar una solicitud y recibiré una respuesta.|  
  
    > [!NOTE]
    >  Bidireccional de recepción puertos no son compatibles con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
     Para obtener más información, consulte [cómo crear un puerto de envío](../../core/how-to-create-a-send-port2.md), o [cómo crear un puerto de recepción](../../core/how-to-create-a-receive-port.md). 
  
-   Si el adaptador envía mensajes a SQL Server (operaciones de salida) o recibe mensajes de SQL Server (operaciones de entrada). Dependiendo de si desea enviar o recibir mensajes, se crea un envío o puerto de recepción, respectivamente.  
  
    > [!NOTE]
    >  También puede configurar el envío o puertos de recepción mediante la importación de un archivo de configuración de enlace que se crea mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] como parte de la generación de metadatos. Para obtener instrucciones acerca de cómo configurar los puertos que utilizan este archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para utilizar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar un puerto mediante el adaptador de WCF-custom y el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)  
  
-   [Configurar un puerto mediante el adaptador de WCF-SQL](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-sql-adapter.md)  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)