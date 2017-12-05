---
title: "Paso 3: Crear la aplicación de LOB de Contoso se asigna para el precio y disponibilidad proyecto utilizando el asignador de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: private process tutorial, creating LOB maps
ms.assetid: a947e0ac-f0cb-4be9-85a8-09daf3675b1a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fef0f6e951798dd2453aa387d8dcde9853968f3a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-creating-the-contoso-lob-application-maps-for-the-price-and-availability-project-using-biztalk-mapper"></a>Paso 3: Crear las asignaciones de aplicación de LOB de Contoso para el precio y el proyecto de disponibilidad mediante el asignador de BizTalk
En este paso, creará dos asignaciones que definen la transformación debe intercambiar correctamente los mensajes entre los dos socios comerciales. En este escenario, el sistema ERP de Contoso ya ha estandarizado en un formato de mensaje para una solicitud de precio y disponibilidad. Los dos mapas asignarán los mensajes de solicitud y respuesta del socio comercial, Fabrikam, a y desde los mensajes de Contoso definidos internamente, respectivamente.  
  
### <a name="to-add-a-reference-for-the-3a2-priceandavailability-request-schema"></a>Para agregar una referencia para el esquema de solicitud de PriceAndAvailability 3A2  
  
1.  En el Explorador de soluciones, haga clic en el proyecto ContosoPriceAndAvailability y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el cuadro de diálogo Agregar referencia, haga clic en **Examinar**.  
  
3.  Desplácese a la carpeta  *\<unidad\>*: \Program BizTalk \<versión\> Accelerator for RosettaNet\Bin y, a continuación, seleccione la  **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll** ensamblado.  
  
4.  Haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-create-the-3a2-priceandavailability-request-to-contoso-priceandavailability-request-map"></a>Para crear la solicitud de PriceAndAvailability 3A2 al mapa de la solicitud de Contoso PriceAndAvailability  
  
1.  En el Explorador de soluciones, haga clic en el proyecto ContosoPriceAndAvailability, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En Agregar nuevo elemento - ContosoPriceAndAvailability cuadro de diálogo, seleccione **archivos de asignación** en el panel de categorías y, a continuación, seleccione **mapa** en el **plantillas** panel. En el **nombre** , escriba **PIP3A2RequestToContosoPriceRequest**y, a continuación, haga clic en **agregar**.  
  
### <a name="to-associate-the-schemas-for-the-pip3a2requesttocontosopricerequest-map"></a>Para asociar los esquemas para la asignación de PIP3A2RequestToContosoPriceRequest  
  
1.  En el asignador de BizTalk (con PIP3A2RequestToContosoPriceRequest.btm muestra), en el panel de esquema de origen, haga clic en **Abrir esquema de origen**.  
  
2.  En el cuadro de diálogo Selector de tipos de BizTalk, expanda **ContosoPriceAndAvailability**, expanda **referencias**, expanda **Microsoft.Solutions.BTARN.Schemas.RNPIPs**y, a continuación, Expanda **esquemas.**  
  
3.  Seleccione **Microsoft.Solutions.BTARN.Schemas.RNPIPs.**  
  
     **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.  
  
5.  En el cuadro de diálogo Selector de tipos de BizTalk, expanda **ContosoPriceAndAvailability**y, a continuación, expanda **esquemas**.  
  
6.  Seleccione el **ContosoPriceAndAvailability.ContosoPriceSchema** esquema y, a continuación, haga clic en **Aceptar**.  
  
7.  En el nodo raíz para esquema de destino, cuadro de diálogo, seleccione la **rootPriceRequest** esquema y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-link-schema-fields-in-the-pip3a2requesttocontosopricerequest-map"></a>Para vincular los campos de esquema en el mapa de PIP3A2RequestToContosoPriceRequest  
  
1.  En el panel de esquema de destino, haga clic en el  **\<esquema\>**  nodo y, a continuación, haga clic en **Expandir nodo de árbol**.  
  
2.  En el panel de esquema de origen, haga clic en el  **\<esquema\>**  nodo y, a continuación, haga clic en **Expandir nodo de árbol**.  
  
3.  Arrastre el **GlobalProductIdentifier** campo a la **ProductID** campo en el panel de esquema de destino.  
  
    > [!NOTE]
    >  Puede encontrar el **GlobalProductIdentifier** campo en el nodo Pip3A2PriceAndAvailabilityQuery/ProductPriceAndAvailabilityQuery /  
    >   
    >  ProductPriceAndAvailability/ProductLineItem/productUnit /  
    >   
    >  ProductPackageDescription/ProductIdentification.  
  
4.  En el **archivo** menú, haga clic en **guardar todo** para guardar los cambios.  
  
## <a name="see-also"></a>Vea también  
 [Creación y configuración de puertos de BizTalk para Contoso](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)