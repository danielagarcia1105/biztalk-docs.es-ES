---
title: Comunicación entre OrderBroker y OrderManager | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, publishing [MessageBox database]
- MessageBox database, publishing
ms.assetid: 1b77dcd2-f7a5-4013-b9a2-c06ace161792
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f438b0dfe744aae5867943f4b1493bb163994f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231876"
---
# <a name="communication-between-orderbroker-and-ordermanager"></a>Comunicación entre OrderBroker y OrderManager
El agente de pedido y las orquestaciones de administrador de pedidos (**OrderBroker**, **OrderManager**) se comunican a través del cuadro de mensajes base de datos en lugar de estar directamente enlazadas. Esto garantiza que el agente y el administrador estén flexiblemente acoplados de modo que, si fuera necesario, puedan ubicarse en grupos separados de BizTalk y ubicaciones geográficamente separadas. Separar las orquestaciones de esta forma requiere sólo configuración administrativa y no requiere ningún cambio de código.  
  
 En la solución configurada actualmente, el agente de pedidos marca mensajes para un administrador de pedidos determinado y los envía a la base de datos de cuadro de mensajes. A su vez, el administrador de pedidos filtra los mensajes destinados a él y toma los mensajes del cuadro de mensajes. Este direccionamiento indirecto: comunicarse a través del cuadro de mensajes, en lugar de enlazar directamente — facilita el proceso mover el agente y el administrador para separar grupos.  
  
 Si hay grupos diferentes responsables de mantener al agente y al administrador, o si deben estar en ubicaciones geográficamente separadas, este diseño lo facilita. Lo único que necesita es mover las orquestaciones a diferentes grupos de BizTalk. Una vez que las orquestaciones están en grupos separados, para volver a conectarlas basta con crear puertos. En el grupo del agente de pedidos, debe crear un puerto de envío que tenga el mismo filtro que el del administrador de pedidos, pero que reenvíe el mensaje al nuevo grupo. En el grupo del administrador de pedidos, debe crear un puerto de recepción que reciba el mensaje y lo coloque en la base de datos de cuadro de mensajes.  
  
 Puede mover las aplicaciones exportándolas para crear archivos MSI, una para el agente y otra para el administrador. Para obtener más información acerca de cómo exportar aplicaciones, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md)