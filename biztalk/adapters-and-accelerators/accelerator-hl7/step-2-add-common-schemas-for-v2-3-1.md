---
title: 'Paso 2: Adición de esquemas comunes para v2.3.1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da98fe6c-4776-4cb8-8454-af3128dea4ab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b07419b50d02d1f810dffbd7417533e844a3ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994165"
---
# <a name="step-2-add-common-schemas-for-v231"></a>Paso 2: Adición de esquemas comunes para v2.3.1
En este paso, creará un nuevo proyecto basado en la plantilla de proyecto BTAHL7231Common. Esta plantilla contiene los tres esquemas comunes (para los tipos de datos, segmentos y valores de tabla) que Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se utiliza para validar las instancias de mensaje v2.3.1. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] utiliza estos esquemas comunes junto con los esquemas HL7 v2.3.1, incluido el esquema que se va a utilizar para los mensajes individuales del lote entrante (ADT ^ A03).  
  
 Al final del paso, asigne una clave segura para el ensamblado e implemente. No es necesario que crear una segunda clave segura; Puede usar la clave segura que creó en [paso 1: agregar esquemas de encabezado y confirmación](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md).  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a>Para agregar los esquemas comunes v2.3.1 e implementar el ensamblado  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2. En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.  
  
3. En el **plantillas** sección, seleccione **proyecto BTAHL7V231Common**.  
  
4. En el **nombre** , escriba **proyecto BTAHL7V231Common** como el nombre del proyecto.  
  
5. En el **solución** cuadro, seleccione **agregar a solución**.  
  
6. Haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  En el Explorador de soluciones, los tres esquemas (datatypes_231.xsd, segments_231.xsd y tablevalues_231.xsd) se incluyen en el proyecto.  
  
7. En el Explorador de soluciones, haga clic en **proyecto BTAHL7V231Common**y, a continuación, haga clic en **propiedades**.  
  
8. En el cuadro de diálogo páginas de propiedades BTAHL7V231Common, haga clic en **firma**.  
  
9. Comprobar **firmar el ensamblado** casilla de verificación.  
  
10. En Elija un archivo de clave de nombre seguro lista desplegable de la lista, seleccione.  
  
11. Vaya a **: Tutorial \Batching**, seleccione **key.snk**y, a continuación, haga clic en **abierto**.  
  
12. Haga clic en **BTAHL7V231Common**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece el mensaje correcto, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.  
  
    Continúe con [paso 3: agregar un esquema del desencadenador de eventos (mensaje)](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).