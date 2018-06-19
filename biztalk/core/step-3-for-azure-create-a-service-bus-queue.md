---
title: 'Paso 3 (para Azure): Crear una cola de Bus de servicio | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7192c3c-4ebf-49c4-b8ce-46a6e9fb5f4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55b3222798edb245000cdde8de52565c39758a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277340"
---
# <a name="step-3-for-azure-create-a-service-bus-queue"></a>Paso 3 (para Azure): Crear una cola de Bus de servicio
En este tema, creará una cola de Service Bus a la que se envía el pedido de ventas X12 después de procesarse y transformarse mediante el acuerdo EDI.  
  
### <a name="to-create-a-service-bus-queue"></a>Para crear una cola de Service Bus  
  
1.  Inicie sesión en el [Portal de administración de Windows Azure CTP](http://go.microsoft.com/fwlink/p/?LinkId=202886) con su cuenta de Microsoft.  
  
2.  En la parte inferior izquierda de la página, haga clic en **AppFabric**.  
  
3.  Amplíe los servicios en el árbol de la parte izquierda, expanda su suscripción y haga clic en el espacio de nombres que ya debe haber creado. Si no dispone ya de un espacio de nombres, vea [Cómo: crear o modificar un Namespace de servicio de Windows Azure CTP](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx).  
  
4.  Para crear una cola, haga clic en **nueva cola** desde el **administrar entidades** categoría desde la barra de herramientas en la parte superior de la página.  
  
5.  En el **nueva cola** diálogo cuadro, escriba un nombre para la cola. Para este tutorial, escriba el nombre como `queueordersedi`y, a continuación, haga clic en **Aceptar**. Ha especificado este nombre como parte del acuerdo EDI que creó en [(para Azure) del paso 2: crear un acuerdo de EDI](../core/step-2-for-azure-create-an-edi-agreement.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)