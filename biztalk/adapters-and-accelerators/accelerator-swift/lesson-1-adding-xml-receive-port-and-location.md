---
title: 'Lección 1: Agregar XML puerto de recepción y ubicación | Microsoft Docs'
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
ms.assetid: 252bc080-3820-44cc-8749-715869f3f684
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51a6f5665fe460084319401e24090a8e92ea8987
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010237"
---
# <a name="lesson-1-adding-xml-receive-port-and-location"></a>Lección 1: Agregar puerto y la ubicación de recepción de XML
Un puerto de recepción es una agrupación lógica de ubicaciones de recepción similares. Una ubicación de recepción define una dirección específica (por ejemplo, una dirección URL o ubicación) para un mensaje entrante y la canalización que se utiliza para procesar el mensaje.  
  
### <a name="to-add-a-receive-port"></a>Para agregar un puerto de recepción  
  
1. Iniciar **administración de BizTalk Server** consola.  
  
   > [!NOTE]
   >  La consola de administración de BizTalk Server también se puede abrir desde dentro de Visual Studio, haga clic en **administración de BizTalk Server** en el **herramientas** menú.  
  
2. En la consola de administración de BizTalk Server, expanda el **administración de BizTalk Server** nodo, el **grupo de BizTalk** nodo, el **aplicaciones** nodo y, a continuación, el **BizTalk Application 1** nodo.  
  
3. Haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
4. En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba **MT103_XML_ReceivePort**.  
  
5. Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar.**  
  
6. Haga clic en **ubicaciones de recepción**, apunte a **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
7. En el cuadro de diálogo un puerto de recepción, seleccione, haga clic en **MT103_XML_ReceivePort**y, a continuación, haga clic en **Aceptar**.  
  
8. En el cuadro de diálogo Propiedades de ubicación de recepción, en el **nombre** , escriba **MT103_XML_ReceiveLocation**.  
  
9. En el **transporte** sección, para el **tipo** cuadro de texto, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.  
  
10. Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipos.  
  
11. En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**. Mover a la  **\<unidad\>: \Labs** carpeta y, a continuación, haga clic en **crear nueva carpeta**.  
  
12. En el cuadro de diálogo Buscar carpeta, cree un **entrante** carpeta  **\<unidad\>: \Labs**y, a continuación, cree un **XMLFile** carpeta  **\<unidad\>: \Labs\Inbound**. Haga clic en **Aceptar**.  
  
13. En el cuadro de diálogo Propiedades de transporte de archivo, asegúrese de que  **\*.xml** se escribe en el **máscara de archivo** cuadro y, a continuación, haga clic en **Aceptar**.  
  
14. En el cuadro de diálogo Propiedades de ubicación de recepción, asegúrese de que **BizTalkServerApplication** se haya especificado para el **controlador de recepción** cuadro.  
  
15. Para el **canalización de recepción** cuadro, seleccione **XMLReceive** en la lista desplegable.  
  
16. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
17. En la consola de administración de BizTalk Server, haga clic en **ubicaciones de recepción**, haga clic en **MT103_XML_ReceiveLocation**y, a continuación, haga clic en **habilitar**.  
  
    > [!NOTE]
    >  Después de habilitar la ubicación de recepción, BizTalk sondea activamente la carpeta de archivos.  
  
    Continúe con [lección 2: agregar el puerto de envío de archivos planos](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-a-flat-file-send-port.md).