---
title: Crear una instancia de mensaje correcto a partir de un PIP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message templates
- PIPs, message templates
ms.assetid: fed3698c-25d9-40ca-878a-60171f425bec
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 040fee5fab56a1e54b777fc7548b8ff28e5b07ec
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960690"
---
# <a name="creating-a-well-formed-message-instance-from-a-pip"></a>Crear una instancia de mensaje correcto a partir de un PIP
En este tema se describe cómo generar una instancia de mensaje correcto. Puede generar una plantilla para una instancia de mensaje a partir del Proceso de interfaz de socio (PIP). Después de hacerlo, debe modificar la plantilla para que sea correcta antes de agregar los datos.  
  
### <a name="to-generate-a-message-instance-template-from-the-pip"></a>Para generar una plantilla de instancia de mensaje a partir del PIP  
  
1.  Inicie **Microsoft Visual Studio 2012**.  
  
2.  En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.  
  
3.  Busque \< *unidad*\>\Program BizTalk \<versión\> Accelerator for RosettaNetSDK\Schemas, haga clic en **RNPIPs.btproj**, y, a continuación, haga clic en **abiertos**.  
  
4.  En el Explorador de soluciones, expanda **RNPIP**y haga clic con el botón derecho en el PIP para el que desea crear una instancia.  
  
5.  Haga clic en **Generar instancia**.  
  
    > [!NOTE]
    >  De este modo se genera un archivo con el nombre del PIP, con "_output" anexado al nombre de archivo y una extensión .xml. Una instrucción en el panel de salida indica dónde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] generó la instancia.  
  
### <a name="to-modify-the-message-instance-template"></a>Para modificar la plantilla de instancia de mensaje  
  
1.  En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, busque la carpeta que contiene el archivo XML y haga doble clic en el nombre de archivo para abrir la carpeta.  
  
2.  Agregue una etiqueta de encabezado XML antes del resto del texto que indique la versión del XML y la codificación. Por ejemplo:  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" ?>  
    ```  
  
3.  Después de la línea que acaba de agregar, agregue una línea DOCTYPE que indique la DTD. Por ejemplo, para una instancia de solicitud de pedido de compra 3A4, la línea sería como se indica a continuación:  
  
    ```  
    <!DOCTYPE Pip3A4PurchaseOrderRequest SYSTEM "3A4_MS_V02_02_PurchaseOrderRequest.dtd">  
    ```  
  
    > [!NOTE]
    >  Cada instancia de mensaje debe incluir la línea DOCTYPE que va a procesarse.  
  
4.  Ahora puede personalizar esta instancia de mensaje para adaptarla a sus necesidades empresariales. Modifique la instancia XML de modo que no use espacios de nombres XML o prefijos de espacios de nombres.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)