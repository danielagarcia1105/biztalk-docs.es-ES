---
title: 'Paso 2: Crear los esquemas comunes para V2.3.1 | Microsoft Docs'
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
ms.openlocfilehash: e6331538a3dd46dcd45d63bcbdbc3b8f19b2c531
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995413"
---
# <a name="step-2-create-common-schemas-for-v231"></a>Paso 2: Crear los esquemas comunes para V2.3.1
Los esquemas V2.3.1 son esquemas normalmente se hace referencia, que se utilizan para validar la instancia de mensaje.  
  
### <a name="to-create-a-common-schema-for-v231"></a>Para crear un esquema comunes para V2.3.1  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2. En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.  
  
3. En la sección plantillas, seleccione **proyecto BTAHL7V231Common**.  
  
4. En el **nombre** , escriba **proyecto BTAHL7V231Common** como el nombre del proyecto.  
  
5. En el **solución** cuadro, seleccione **agregar a solución**.  
  
6. Haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  En el Explorador de soluciones, los tres esquemas (datatypes_231.xsd, segments_231.xsd y tablevalues_231.xsd) se incluyen en el proyecto.  
  
7. En el Explorador de soluciones, haga clic en **proyecto BTAHL7V231Common**y, a continuación, haga clic en **propiedades**.  
  
8. En la página de propiedades BTAHL7V231Common, haga clic en **firma**.  
  
9. Seleccione el **firmar el ensamblado** casilla de verificación.  
  
10. En **elegir un archivo de clave de nombre seguro**, seleccione  **\<Examinar... \>** .  
  
11. Vaya a \<unidad\>: Tutorial, seleccione \Batching **key.snk**y, a continuación, haga clic en **abierto**.  
  
12. En el Explorador de soluciones, haga clic en **proyecto BTAHL7V231Common**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece el mensaje correcto, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.  
  
    Continúe con [paso 3: agregar un esquema del desencadenador de eventos (mensaje)](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).