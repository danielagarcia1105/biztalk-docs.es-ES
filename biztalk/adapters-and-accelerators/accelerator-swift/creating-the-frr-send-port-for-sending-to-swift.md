---
title: "Crear el puerto de envío FRR para enviar a SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 1ad766db-d1da-437a-a520-a3b04f0695c4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75cbda5d505f17f2dd7462cb0b16868a340f625c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a>Crear el puerto de envío FRR para enviar para SWIFT
Para realizar la conciliación de respuesta de FIN, debe crear un puerto de envío que envía un mensaje de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a la red SWIFT.  
  
 **Resumen**  
  
 Crear un puerto de envío con los componentes y las propiedades siguientes:  
  
|Propiedad/componente|Configuración|  
|-------------------------|-------------|  
|Puerto de envío|Puerto unidireccional estático|  
|Tipo de transporte|MQSeries|  
|Definición de la cola (MQSeries)|Administrador de cola de MQSeries server cola|  
|Canalización de envío|El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de envío que ha creado para FRR|  
|Filtros|Como se muestra en la tabla siguiente|  
  
### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a>Para agregar un puerto de envío personalizada para enviar a SWIFT  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto estático de una waySend**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba un nombre para el puerto de envío, por ejemplo, FRRSWIFTSendPort.  
  
3.  Para **tipo**, seleccione **MQSeries**.  
  
4.  Haga clic en **configurar**.  
  
5.  En el cuadro de diálogo Propiedades de transporte MQSeries, haga clic en **definición de la cola**y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
6.  En el cuadro de diálogo Definición de la cola, especifique el servidor, un administrador de cola y una cola de MQSeries. Haga clic en **Aceptar**.  
  
7.  En el cuadro de diálogo Propiedades de transporte MQSeries, compruebe que las propiedades son según sea necesario. Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Para obtener más información acerca de las propiedades de transporte de MQSeries, consulte la documentación de MQSeries.  
  
8.  En el cuadro de diálogo Propiedades de puerto de envío, para **controlador de envío**, compruebe que está seleccionado BizTalkServerApplication.  
  
9. Para **canalización de envío**, seleccione la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de envío que ha creado para FRR.  
  
10. Haga clic en **filtros** en el panel izquierdo y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **False**.|  
    |**Grupo**|Seleccione **y**.|  
    |**Propiedad**|Tipo de **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **True**.|  
  
11. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
12. Haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.