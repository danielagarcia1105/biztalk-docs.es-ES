---
title: "Lección 2: Agregar un puerto de envío XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, XML ports
- XML ports
ms.assetid: 03b2ee43-7874-4ef9-b716-8e16e96d8382
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23d8aac412bf81492793eec2f4936d84b54fda0d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-2-adding-an-xml-send-port"></a>Lección 2: Agregar un puerto de envío de XML
Use un puerto de envío para definir cómo desea que los mensajes enviados. En esta lección, creará un puerto de envío para definir cómo se deberían enviar los mensajes XML.  
  
### <a name="to-add-an-xml-send-port"></a>Para agregar un puerto de envío XML  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba **MT103_XML_SendPort**.  
  
3.  En el **transporte** sección, para la **tipo** cuadro, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.  
  
4.  Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.  
  
5.  En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.  
  
6.  En el cuadro de diálogo Buscar carpeta, desplácese a la  **\<unidad\>: \Labs\Outbound** carpeta y, a continuación, haga clic en **Aceptar**.  
  
7.  En el cuadro de diálogo Propiedades de transporte de archivo, asegúrese de que **%MessageID%.xml** se escribe en el **nombre de archivo** cuadro y, a continuación, haga clic en **Aceptar**.  
  
8.  En el cuadro de diálogo Propiedades de puerto de envío, asegúrese de que **BizTalkServerApplication** está seleccionada para la **controlador de envío** cuadro y que **PassThruTransmit** está seleccionada para el **Canalización de envío** cuadro.  
  
9. En el panel izquierdo, haga clic en **filtros**, y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **BTS. ReceivePortName**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **MT103_FlatFile_ReceivePort**.|  
    |**Grupo**|Seleccione **y**.|  
  
10. Haga clic dentro de la siguiente línea de propiedad y haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **False** para mensajes válidos.|  
  
    > [!NOTE]
    >  Agrega el **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False"** cláusula de expresión de filtro para que el puerto de envío envía solo correctamente analizar y validar mensajes. A diferencia de una canalización de recepción mediante nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] desensambladores, el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Desensamblador no suspenderá un mensaje con errores (erróneo), pero en su lugar, se publica en el cuadro de mensajes y marcas como error, utilizando las propiedades promocionadas. A4SWIFT asocia una representación XML de los errores que se recopilaron para el mensaje con errores antes de publicarlos en el cuadro de mensajes.  
    > Sin incluir la "Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False" cláusula de expresión de filtro, el puerto de envío enviará todos los mensajes: superado o no superado. Para obtener más información acerca de las suscripciones de mensajes con errores, vea [trabajar con suscripciones de mensajes de error](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).  
  
11. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
12. En la consola de administración de BizTalk Server, en **puertos de envío**, haga clic en **MT103_XML_SendPort**y, a continuación, haga clic en **iniciar**.  
  
 Continúe con [módulo 6: implementar las reglas de negocios](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md).