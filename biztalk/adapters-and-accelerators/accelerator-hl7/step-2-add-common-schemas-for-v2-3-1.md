---
title: 'Paso 2: Agregar los esquemas comunes para v2.3.1 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da98fe6c-4776-4cb8-8454-af3128dea4ab
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba84c9f45c477aefe7615eca906c40014b06bd04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-add-common-schemas-for-v231"></a>Paso 2: Agregar los esquemas comunes para v2.3.1
En este paso, creará un proyecto nuevo basado en la plantilla de proyecto de BTAHL7231Common. Esta plantilla contiene los tres esquemas comunes (para tipos de datos, segmentos y valores de tabla) que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se utiliza para validar las instancias de mensaje v2.3.1. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]estos esquemas comunes se utiliza junto con los esquemas de v2.3.1 HL7, incluido el esquema que se va a utilizar para los mensajes individuales del lote entrante (ADT ^ A03).  
  
 Al final del paso que asigne una clave segura para el ensamblado y se implemente. No tienes que volver a crear una segunda clave segura; Puede usar la clave segura que creó en [paso 1: agregar encabezado y esquemas de confirmación](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md).  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a>Para agregar los esquemas comunes de v2.3.1 e implementar el ensamblado  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.  
  
3.  En el **plantillas** sección, seleccione **proyecto BTAHL7V231Common**.  
  
4.  En el **nombre** cuadro, escriba **proyecto BTAHL7V231Common** como el nombre del proyecto.  
  
5.  En el **solución** cuadro, seleccione **agregar a solución**.  
  
6.  Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  En el Explorador de soluciones, se incluyen tres esquemas (datatypes_231.xsd, segments_231.xsd y tablevalues_231.xsd) en el proyecto.  
  
7.  En el Explorador de soluciones, haga clic en **proyecto BTAHL7V231Common**y, a continuación, haga clic en **propiedades**.  
  
8.  En el cuadro de diálogo páginas de propiedades de BTAHL7V231Common, haga clic en **firma**.  
  
9. Comprobar **firmar el ensamblado** casilla de verificación.  
  
10. En Elija un archivo de clave de nombre seguro lista desplegable lista, seleccione.  
  
11. Vaya a **: \Batching Tutorial**, seleccione **key.snk**y, a continuación, haga clic en **abiertos**.  
  
12. Haga clic en **BTAHL7V231Common**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece el mensaje correcto, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.  
  
 Continúe con [paso 3: agregar un esquema de eventos (mensaje) desencadenador](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).