---
title: "Cómo crear puertos de envío para JD Edwards OneWorld | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 858425ef-bdb7-4d2d-90ca-b3655e389749
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc77fd72171983ab2fbc7de42ddf36d770d045c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a>Creación de puertos de envío para JD Edwards OneWorld
Use el procedimiento siguiente para crear un puerto de envío.  
  
### <a name="to-create-a-send-port"></a>Procedimiento para crear un puerto de envío  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, navegue hasta el aplicación necesaria.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
    > [!NOTE]
    >  También puede usar **Puerto unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** , a continuación, escriba un nombre de puerto de envío (por ejemplo, escriba **SendToJDE**.)  
  
4.  En el **tipo** lista desplegable, seleccione **JDEOneWorld**.  
  
5.  En el **URI** lista desplegable, seleccione el controlador de envío.  
  
6.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear controladores de envío de OneWorld JD Edwards](../core/creating-jd-edwards-oneworld-send-handlers.md)