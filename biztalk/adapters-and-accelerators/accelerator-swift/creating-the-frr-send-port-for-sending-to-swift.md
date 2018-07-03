---
title: Crear el puerto de envío FRR para enviar a SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 1ad766db-d1da-437a-a520-a3b04f0695c4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1583072986eba20b5a0202e6973a5c08095aab01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972325"
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a>Crear el puerto de envío FRR para enviar a SWIFT
Para llevar a cabo la conciliación de respuestas de FIN, deberá crear un puerto de envío que envía un mensaje de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a la red SWIFT.  

 **Resumen**  

 Cree un puerto de envío con los componentes y las propiedades siguientes:  


|     Propiedad o el componente      |                                                               Configuración                                                                |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
|          Puerto de envío          |                                                         Puerto unidireccional estático                                                          |
|       Tipo de transporte        |                                                               MQSeries                                                               |
| Definición de la cola (MQSeries) |                                                 Administrador de cola de MQSeries server cola                                                  |
|        Canalización de envío        | El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de envío que ha creado para FRR |
|           Filtros           |                                                     Como se muestra en la tabla siguiente                                                      |

### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a>Para agregar un puerto de envío personalizada para enviar a SWIFT  

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto estático de uno waySend**.  

2. En el cuadro de diálogo Propiedades de puerto de envío, en el **nombre** , escriba un nombre para el puerto de envío, como FRRSWIFTSendPort.  

3. Para **tipo**, seleccione **MQSeries**.  

4. Haga clic en **configurar**.  

5. En el cuadro de diálogo Propiedades de transporte MQSeries, haga clic en **definición de la cola**y, a continuación, haga clic en el botón de puntos suspensivos (...).  

6. En el cuadro de diálogo Definición de la cola, especifique el servidor, Administrador de cola y cola de MQSeries. Haga clic en **Aceptar**.  

7. En el cuadro de diálogo Propiedades de transporte MQSeries, compruebe que las propiedades son según sea necesario. Haga clic en **Aceptar**.  

   > [!NOTE]
   >  Para obtener más información acerca de las propiedades de transporte de MQSeries, vea la documentación de MQSeries.  

8. En el cuadro de diálogo Propiedades de puerto de envío para **controlador de envío**, compruebe que está seleccionado BizTalkServerApplication.  

9. Para **canalización de envío**, seleccione el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de envío que ha creado para FRR.  

10. Haga clic en **filtros** en el panel izquierdo y, a continuación, haga lo siguiente:  


    |   Use   |                            Para                             |
    |--------------|-------------------------------------------------------------------|
    | **Propiedad** |  Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.  |
    | **Operador** |                          Seleccione **==**.                           |
    |  **Value**   |                          Tipo **False**.                          |
    |  **Grupo**   |                          Seleccione **y**.                          |
    | **Propiedad** | Tipo **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**. |
    | **Operador** |                          Seleccione **==**.                           |
    |  **Value**   |                          Tipo **True**.                           |


11. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  

12. Haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.
