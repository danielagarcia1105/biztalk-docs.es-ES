---
title: "Lección 2: Agregar un puerto de envío de archivo sin formato | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, flat files
- flat files, send ports
- creating, send ports
- send ports, creating
ms.assetid: 33dceb0d-85f5-4e19-820f-cd33b60cd32a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1370b4877c2e32055e2ee0a0aca1f922bd8668a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a>Lección 2: Agregar un puerto de envío de archivo sin formato
En esta lección, configurará el puerto de envío y la ubicación de envío. Utilice el puerto de envío para definir cómo desea que los mensajes enviados. También crea una ubicación de carpeta de archivos para los mensajes enviados.  
  
### <a name="to-add-a-flat-file-send-port"></a>Para agregar un puerto de envío de archivo sin formato  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba **MT103_FlatFile_SendPort**.  
  
3.  En el **transporte** sección, para la **tipo** cuadro, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.  
  
4.  Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.  
  
5.  En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.  
  
6.  En el cuadro de diálogo Buscar carpeta, desplácese a la  **\<unidad >: \Labs** carpeta y, a continuación, haga clic en **crear nueva carpeta**.  
  
7.  Crear un **saliente** carpeta  **\<unidad >: \Labs**y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **nombre de archivo** , escriba **%MessageID%.txt**y, a continuación, haga clic en **Aceptar**.  
  
9. En el cuadro de diálogo Propiedades de puerto de envío, haga clic en la lista desplegable para la **canalización de envío** cuadro y, a continuación, seleccione **MT103SendPipeline**.  
  
10. En el panel izquierdo, haga clic en **filtros**, y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **BTS. ReceivePortName**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **MT103_XML_ReceivePort**.|  
  
11. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**  
  
12. En el **puertos de envío** panel, haga clic en **MT103_FlatFile_SendPort**y, a continuación, haga clic en **iniciar**.  
  
 Continúe con [módulo 5: agregar un archivo plano ubicación de recepción y puertos de envío XML](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md).