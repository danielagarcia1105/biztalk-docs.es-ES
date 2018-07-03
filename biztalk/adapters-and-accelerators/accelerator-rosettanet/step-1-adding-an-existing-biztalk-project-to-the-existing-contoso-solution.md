---
title: 'Paso 1: Agregar un proyecto de BizTalk existente a la solución de Contoso existente | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, adding to solutions
- private process tutorial, adding projects to solutions
ms.assetid: 9e84d282-01aa-4611-8462-c1acef234042
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9491c52bfbcbc78e2897cf509b1be320bb223e19
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010245"
---
# <a name="step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution"></a>Paso 1: Agregar un proyecto de BizTalk existente a la solución de Contoso existente
The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK contiene una orquestación de procesos privado que actúa como un buen punto de partida al personalizar su propio proceso privado. En este paso, se agregue esa orquestación a la solución y cambiar el nombre del ensamblado para evitar conflictos con la orquestación PrivateResponder instalada durante el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] instalación. Antes de empezar, abra la solución de Contoso ha creado en [paso 1: crear una nueva solución de BizTalk para el Contoso Price y solicitud de disponibilidad](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md).  
  
### <a name="to-add-the-privateresponder-project-to-the-contoso-solution"></a>Para agregar el proyecto de PrivateResponder a la solución de Contoso  
  
1.  Copie el ejemplo de PrivateResponder SDK en la carpeta de su solución de Contoso.  
  
    > [!NOTE]
    >  De forma predeterminada, el ejemplo de PrivateResponder SDK se encuentra en C:\Program Files\Microsoft BizTalk \<versión\> Acelerador de la carpeta RosettaNet\SDK\PrivateResponder.  
  
2.  En Visual Studio, haga clic en **archivo**, apunte a **agregar**y, a continuación, haga clic en **proyecto existente**.  
  
3.  En el cuadro de diálogo Agregar proyecto existente, busque la carpeta de la solución, seleccione el **PrivateResponder.btproj** archivo de proyecto y, a continuación, haga clic en **abierto**.  
  
### <a name="to-change-the-privateresponder-assembly-name-and-default-namespace"></a>Para cambiar el nombre del ensamblado PrivateResponder y espacio de nombres predeterminado  
  
1.  En el Explorador de soluciones, haga clic la **PrivateResponder** del proyecto y, a continuación, haga clic en **propiedades**.  
  
2.  En el cuadro de diálogo páginas de propiedades de PrivateResponder, en el árbol de consola, haga clic en **General**. En el panel de detalles, en la **nombre del ensamblado** , escriba **ContosoPriceAndAvailability.PrivateResponder**.  
  
3.  En el **Default Namespace** , escriba **ContosoPriceAndAvailability**.  
  
4.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo páginas de propiedades de PrivateResponder.  
  
5.  En el Explorador de soluciones, haga doble clic en **PrivateResponder.odx**.  
  
6.  En el **Vista orquestación** ventana, asegúrese de que **propiedades de orquestación** (bajo **PrivateResponderProcess**) está seleccionado.  
  
7.  En el **propiedades** ventana, en el **Namespace** , escriba **ContosoPriceAndAvailability**y, a continuación, presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Definición y publicación del vocabulario de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)