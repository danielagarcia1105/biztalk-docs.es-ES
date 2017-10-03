---
title: "Crear un puerto de envío de A4SWIFT | Documentos de Microsoft"
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
ms.assetid: d1ee18f8-a6aa-4cd5-9e65-fb2e0fa2d0c2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cf24cb99643acc869123450ce14fd5050ee7408
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-an-a4swift-send-port"></a>Crear un puerto de envío de A4SWIFT
Debe crear un puerto de envío para habilitar [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] para enviar un mensaje a la red SWIFT, tal como se muestra en la ilustración siguiente. Este puerto de envío enviará mensajes de archivo sin formato en una carpeta de archivo de salida. Este puerto de envío está diseñado para trabajar con la característica de reparación de mensajes y nuevo envío.  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")  
  
 **Resumen**  
  
 Crear e iniciar un puerto de envío unidireccional estático con las propiedades y los componentes siguientes:  
  
|Propiedad/componente|Configuración|  
|-------------------------|-------------|  
|Puerto de envío|Puerto unidireccional estático|  
|Tipo de transporte|FILE|  
|Carpeta de destino (URI de dirección)|Nombre de la carpeta que desea enviar mensajes desde|  
|Nombre de archivo (dirección URI)|%MessageID%.txt|  
|Filtros|Como se describe en la tabla siguiente|  
  
### <a name="to-add-the-sent-port"></a>Para agregar el puerto de envío  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba un nombre para el puerto de envío.  
  
3.  En el **transporte** sección, para la **tipo** cuadro, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.  
  
4.  Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.  
  
5.  En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.  
  
6.  En el cuadro de diálogo Buscar carpeta, mover a la carpeta que desea enviar mensajes desde. Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si esta carpeta no existe, puede crearlo mediante el **crear nueva carpeta** comando.  
  
7.  En el **nombre de archivo** , escriba **%MessageID%.txt**y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **propiedades de puerto de envío** diálogo cuadro, haga clic en la lista desplegable para la **canalización de envío** cuadro y, a continuación, seleccione la canalización de envío personalizada.  
  
9. En el panel izquierdo, haga clic en **filtros**, y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **BTS. Operación**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **A4SWIFT_MRSRCompleted**.|  
    |**Grupo**|Seleccione **o.**|  
    |**Propiedad**|Seleccione **BTS. Operación**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **A4SWIFT_MRSRFailed**.|  
    |**Grupo**|Seleccione **o**.|  
    |**Propiedad**|Seleccione **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Tipo de **True**.|  
  
10. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**  
  
11. En el **puertos de envío** panel, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.