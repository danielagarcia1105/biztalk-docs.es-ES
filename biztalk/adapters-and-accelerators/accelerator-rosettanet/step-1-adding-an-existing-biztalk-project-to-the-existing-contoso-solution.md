---
title: "Paso 1: Agregar un proyecto de BizTalk existente a la solución existente de Contoso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects, adding to solutions
- private process tutorial, adding projects to solutions
ms.assetid: 9e84d282-01aa-4611-8462-c1acef234042
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 343bdf83d90d38a6fc0c626a65353c0185c43f6c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution"></a>Paso 1: Agregar un proyecto de BizTalk existente a la solución existente de Contoso
El [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK contiene una orquestación de procesos privados que actúa como un buen punto de partida al personalizar sus propios procesos privados. En este paso, se agrega esa orquestación a la solución y cambie el nombre de ensamblado para evitar el conflicto con la orquestación PrivateResponder que se instalan durante el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] instalación. Antes de empezar, abra la solución de Contoso que creó en [paso 1: crear una nueva solución de BizTalk para los Contoso Price y solicitudes de disponibilidad](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md).  
  
### <a name="to-add-the-privateresponder-project-to-the-contoso-solution"></a>Para agregar el proyecto de PrivateResponder a la solución de Contoso  
  
1.  Copie el ejemplo de SDK de PrivateResponder en la carpeta de su solución de Contoso.  
  
    > [!NOTE]
    >  De forma predeterminada, el ejemplo de SDK de PrivateResponder se encuentra en C:\Program Files\Microsoft BizTalk \<versión\> Acelerador de carpeta RosettaNet\SDK\PrivateResponder.  
  
2.  En Visual Studio, haga clic en **archivo**, seleccione **agregar**y, a continuación, haga clic en **proyecto existente**.  
  
3.  En el cuadro de diálogo Agregar proyecto existente, busque la carpeta de la solución, seleccione la **PrivateResponder.btproj** archivo de proyecto y, a continuación, haga clic en **abiertos**.  
  
### <a name="to-change-the-privateresponder-assembly-name-and-default-namespace"></a>Para cambiar el nombre del ensamblado PrivateResponder y espacio de nombres predeterminado  
  
1.  En el Explorador de soluciones, haga clic con el **PrivateResponder** del proyecto y, a continuación, haga clic en **propiedades**.  
  
2.  En el cuadro de diálogo páginas de propiedades de PrivateResponder, en el árbol de consola, haga clic en **General**. En el panel de detalles, en la **nombre de ensamblado** , escriba **ContosoPriceAndAvailability.PrivateResponder**.  
  
3.  En el **Default Namespace** , escriba **ContosoPriceAndAvailability**.  
  
4.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo páginas de propiedades de PrivateResponder.  
  
5.  En el Explorador de soluciones, haga doble clic en **PrivateResponder.odx**.  
  
6.  En el **Vista orquestación** ventana, asegúrese de que **propiedades de orquestación** (en **PrivateResponderProcess**) está seleccionado.  
  
7.  En el **propiedades** ventana, en la **Namespace** , escriba **ContosoPriceAndAvailability**y, a continuación, presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Definición y publicación del vocabulario de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)