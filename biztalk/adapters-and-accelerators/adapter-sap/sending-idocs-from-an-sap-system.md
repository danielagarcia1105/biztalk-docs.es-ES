---
title: Enviar IDOC desde un sistema SAP para usar el adaptador de mySAP en BizTalk | Documentos de Microsoft
description: 
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aea8a5e9-d775-4d52-a434-c2908b53cd2d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63f7d1ccdaa8cb6a4ee12ad1cc4263c487a164c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sending-idocs-from-an-sap-system"></a>Enviar IDOC desde un sistema SAP
Tareas de alto nivel que se complete en el sistema SAP para enviar un IDOC desde el sistema SAP a una aplicación externa. Póngase en contacto con el Administrador de SAP para llevar a cabo estas tareas o consulte las instrucciones de SAP.  
  
## <a name="send-an-idoc-from-sap"></a>Enviar un IDOC desde SAP  
  
1.  Inicie la GUI de SAP.  
  
2.  Crear un sistema lógico con la transacción de BD54.  
  
3.  Crear un destino RFC en conexiones de TCP/IP con la transacción SM59.  
  
4.  Crear un puerto mediante transacciones WE21 y adjuntarlo al destino RFC creado en el último paso.  
  
5.  Crear un perfil de socio comercial mediante transacciones de WE20 con el tipo de mensaje necesario y el tipo IDOC y, a continuación, adjuntarlo al puerto creado en el último paso.  
  
6.  Mantener un modelo distribuido mediante la conexión del tipo de mensaje en el puerto utilizando la transacción de venta.  
  
7.  Generar un IDOC de SAP. Por ejemplo, usar transacciones BD10 para desencadenar un IDOC MATMAS. Para obtener información acerca de otras transacciones para desencadenar el IDOC específico, póngase en contacto con el Administrador de SAP.  

## <a name="view-transaction-ids-in-sap"></a>Id. de transacción de vista en SAP
Cuando el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] invoca un tRFC o envía un IDOC a un sistema SAP, los registros de sistema SAP una transacción TID (Id.) en respuesta. En algunos casos, tendrá que conocer el TID que está registrado con el sistema SAP en respuesta a una llamada desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Por ejemplo, puede identificar la unidad lógica de trabajo (LUW) en el sistema SAP para solucionar un problema.  
  
 Para ver el TID en un sistema SAP, debe usar la transacción SM58. Póngase en contacto con el Administrador de SAP o consulte la Guía de SAP para obtener más información acerca de esta transacción. 

## <a name="view-details-about-idocs-sent-and-received-from-sap"></a>Ver detalles acerca de IDOC enviados y recibidos desde SAP
Mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], puede enviar un IDOC a un sistema SAP o recibir un IDOC desde un sistema SAP. Para realizar un seguimiento del estado y ver los datos de un IDOC envían o reciben por un sistema SAP, puede usar la transacción WE02. Póngase en contacto con el Administrador de SAP o consulte la Guía de SAP para obtener más información acerca de esta transacción.  

  
## <a name="see-also"></a>Vea también  
 [Realizar tareas mediante la GUI de SAP para escenarios de adaptadores SAP específicos](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)