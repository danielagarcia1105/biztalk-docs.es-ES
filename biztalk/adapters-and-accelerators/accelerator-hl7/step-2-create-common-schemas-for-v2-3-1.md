---
title: 'Paso 2: Crear los esquemas comunes para V2.3.1 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, common schemas
- common schemas
ms.assetid: db1a2206-559f-475a-803d-55522cce007e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5f8ed36b4a1ae8553e8df488e8fd5a606c0eabd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960994"
---
# <a name="step-2-create-common-schemas-for-v231"></a>Paso 2: Crear los esquemas comunes para V2.3.1
Los esquemas V2.3.1 son esquemas normalmente se hace referencia, que se utilizan para validar la instancia de mensaje.  
  
### <a name="to-create-a-common-schema-for-v231"></a>Para crear un esquema común para V2.3.1  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.  
  
3.  En la sección de plantillas, seleccione **proyecto BTAHL7V231Common**.  
  
4.  En el **nombre** cuadro, escriba **proyecto BTAHL7V231Common** como el nombre del proyecto.  
  
5.  En el **solución** cuadro, seleccione **agregar a solución**.  
  
6.  Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  En el Explorador de soluciones, se incluyen tres esquemas (datatypes_231.xsd, segments_231.xsd y tablevalues_231.xsd) en el proyecto.  
  
7.  En el Explorador de soluciones, haga clic en **proyecto BTAHL7V231Common**y, a continuación, haga clic en **propiedades**.  
  
8.  En la página de propiedades BTAHL7V231Common, haga clic en **firma**.  
  
9. Seleccione el **firmar el ensamblado** casilla de verificación.  
  
10. En **elegir un archivo de clave de nombre seguro**, seleccione  **\<Examinar... \>** .  
  
11. Vaya a \<unidad\>: Tutorial, seleccione \Batching **key.snk**y, a continuación, haga clic en **abiertos**.  
  
12. En el Explorador de soluciones, haga clic en **proyecto BTAHL7V231Common**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece el mensaje correcto, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.  
  
 Continúe con [paso 3: agregar un esquema de eventos (mensaje) desencadenador](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).