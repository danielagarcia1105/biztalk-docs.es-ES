---
title: "Lección 1: Agregar XML puerto de recepción y ubicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- receive ports, creating
- creating, receive ports
ms.assetid: 252bc080-3820-44cc-8749-715869f3f684
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 186cbb4e021a281ab834f04097f005c2597fbd37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-1-adding-xml-receive-port-and-location"></a>Lección 1: Agregar puerto y la ubicación de recepción de XML
Un puerto de recepción es una agrupación lógica de ubicaciones de recepción similares. Una ubicación de recepción define una dirección específica (por ejemplo, una ubicación de archivo o dirección URL) para un mensaje entrante y la canalización que se utiliza para procesar el mensaje.  
  
### <a name="to-add-a-receive-port"></a>Para agregar un puerto de recepción  
  
1.  Iniciar **administración de BizTalk Server** consola.  
  
    > [!NOTE]
    >  La consola de administración de BizTalk Server también puede abrir desde dentro de Visual Studio, haga clic en **administración de BizTalk Server** en el **herramientas** menú.  
  
2.  En la consola de administración de BizTalk Server, expanda el **administración de BizTalk Server** nodo, la **grupo de BizTalk** nodo, la **aplicaciones** nodo y, a continuación, el **BizTalk Application 1** nodo.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
4.  En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba **MT103_XML_ReceivePort**.  
  
5.  Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar.**  
  
6.  Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
7.  En el, seleccione un cuadro de diálogo de puerto de recepción, haga clic en **MT103_XML_ReceivePort**y, a continuación, haga clic en **Aceptar**.  
  
8.  En el cuadro de diálogo Propiedades de la ubicación de recepción, en el **nombre** , escriba **MT103_XML_ReceiveLocation**.  
  
9. En el **transporte** sección, para la **tipo** cuadro de texto, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.  
  
10. Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.  
  
11. En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**. Mover a la  **\<unidad >: \Labs** carpeta y, a continuación, haga clic en **crear nueva carpeta**.  
  
12. En el cuadro de diálogo Buscar carpeta, cree una **entrada** carpeta en  **\<unidad >: \Labs**y, a continuación, cree un **XMLFile** carpeta  **\<unidad >: \Labs\Inbound**. Haga clic en **Aceptar**.  
  
13. En el cuadro de diálogo Propiedades de transporte de archivo, asegúrese de que  **\*.xml** se escribe en el **máscara de archivo** cuadro y, a continuación, haga clic en **Aceptar**.  
  
14. En el cuadro de diálogo Propiedades de la ubicación de recepción, asegúrese de que **BizTalkServerApplication** se haya especificado para la **controlador de recepción** cuadro.  
  
15. Para el **canalización de recepción** cuadro, seleccione **XMLReceive** en la lista desplegable.  
  
16. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
17. En la consola de administración de BizTalk Server, haga clic en **ubicaciones de recepción**, haga clic en **MT103_XML_ReceiveLocation**y, a continuación, haga clic en **habilitar**.  
  
    > [!NOTE]
    >  Después de habilitar la ubicación de recepción, BizTalk sondea activamente la carpeta de archivos.  
  
 Continúe con [lección 2: agregar el puerto de envío de archivo sin formato](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-a-flat-file-send-port.md).