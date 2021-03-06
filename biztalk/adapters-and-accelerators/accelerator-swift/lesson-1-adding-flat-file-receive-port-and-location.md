---
title: 'Lección 1: Adición de archivos planos puerto de recepción y ubicación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- receive ports, creating
- creating, receive ports
ms.assetid: 881f58d8-f541-4a85-b534-cb1ca627c002
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e23525715be1816684ffa680f99cf8f8bd88ceca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966269"
---
# <a name="lesson-1-adding-flat-file-receive-port-and-location"></a>Lección 1: Adición de archivos planos puerto de recepción y ubicación
El puerto de recepción siempre tiene una ubicación de recepción asociada que se debe configurar al agregar el puerto de recepción. Una ubicación de recepción define una dirección específica para un mensaje entrante y la canalización que use para procesar el mensaje.  
  
### <a name="to-add-a-receive-port"></a>Para agregar un puerto de recepción  
  
1. En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
2. En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba **MT103_FlatFile_ReceivePort**.  
  
3. Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.  
  
4. En la consola de administración de BizTalk Server, haga clic en **ubicaciones de recepción**, apunte a **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
5. En el cuadro de diálogo un puerto de recepción, seleccione, haga clic en **MT103_FlatFile_ReceivePort**y, a continuación, haga clic en **Aceptar**.  
  
6. En el cuadro de diálogo Propiedades de ubicación de recepción, en el **nombre** , escriba **MT103_FlatFile_ReceiveLocation**.  
  
7. En el **transporte** sección, para el **tipo** cuadro de texto, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.  
  
8. Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipos.  
  
9. En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.  
  
10. En el cuadro de diálogo Buscar carpeta, desplácese a la  **\<unidad\>: \Labs\Inbound** carpeta y, a continuación, haga clic en **crear nueva carpeta**.  
  
11. Crear un **FlatFile** carpeta  **\<unidad\>: \Labs\Inbound**y, a continuación, haga clic en **Aceptar**.  
  
12. En el **máscara de archivo** , escriba  **\*.txt**y, a continuación, haga clic en **Aceptar**.  
  
13. En el cuadro de diálogo Propiedades de ubicación de recepción, asegúrese de que **BizTalkServerApplication** se haya especificado para el **controlador de recepción** cuadro.  
  
14. Para el **canalización de recepción** cuadro, seleccione **MT103ReceivePipeline** en la lista desplegable.  
  
15. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
16. En la consola de administración de BizTalk Server, haga clic en **ubicaciones de recepción**, haga clic en **MT103_FlatFile_ReceiveLocation**y, a continuación, haga clic en **habilitar**.  
  
    Continúe con [lección 2: agregar un puerto de envío XML](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).