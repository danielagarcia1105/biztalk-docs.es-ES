---
title: 'Paso 2: Crear un nuevo proyecto | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, projects
- projects, creating
- message enrichment tutorial, projects
ms.assetid: 6e994845-53b8-4de8-a64f-32d36f7b5412
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78cfd1341100fe803679e81300609962a9c0e1f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-a-new-project"></a>Paso 2: Crear un nuevo proyecto
En este paso, se compila una nueva solución mediante la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] entorno. En primer lugar, cree un nuevo proyecto (BTAHL7V22Common) que contiene los tres esquemas comunes (para tipos de datos, segmentos y valores de tabla) que utilizan los esquemas de HL7 V2.2, incluido el esquema que se va a utilizar para el mensaje saliente de HL7. En segundo lugar, compile otro nuevo proyecto (BTAHL7V2XCommon) que contiene el esquema estándar común utilizado para los encabezados de mensajes HL7 (MSH_25_GLO_DEF).  
  
### <a name="to-create-a-new-project"></a>Para crear un nuevo proyecto  
  
1.  Iniciar  **[!INCLUDE[vs2012](../../includes/vs2012-md.md)]** .  
  
2.  En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.  
  
3.  En el cuadro de diálogo nuevo proyecto, expanda el **proyectos de BizTalk** carpeta y, a continuación, haga clic en el **BTAHL7Projects** carpeta.  
  
4.  En el **plantillas** panel, haga clic en **BTAHL7V22Common proyecto**.  
  
5.  En el **nombre** , escriba **BTAHL7V22Common** como el nombre del proyecto.  
  
6.  En el **ubicación** , escriba  *\<unidad >***: \Tutorial** como ruta de acceso y, a continuación, haga clic en **Aceptar** para abrir el nuevo proyecto.  
  
    > [!NOTE]
    >  Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) agrega un nuevo proyecto en el Explorador de soluciones con los tres esquemas comunes:  
  
    -   datatypes_22.xsd  
  
    -   segments_22.xsd  
  
    -   tablevalues_22.xsd  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]crea la carpeta del proyecto y los archivos en el \< *unidad*>: \Tutorial\BTAHL7V22Common carpeta.  
  
7.  En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.  
  
8.  En el cuadro de diálogo nuevo proyecto, expanda el **proyectos de BizTalk** carpeta y, a continuación, haga clic en el **BTAHL7Projects** carpeta.  
  
9. En el **plantillas** panel, haga clic en **proyecto BTAHL7V2XCommon**.  
  
10. En el **nombre** , escriba **BTAHL7V2XCommon** como el nombre del proyecto.  
  
11. En el **ubicación** , escriba  *\<unidad >***: \Tutorial** como la ruta de acceso.  
  
12. En el **solución** campo, seleccione **agregar a solución**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Agrega un nuevo proyecto en el Explorador de soluciones con los siguientes esquemas:  
  
    -   ACK_24_GLO_DEF.xsd  
  
    -   ACK_25_GLO_DEF.xsd  
  
    -   MSH_25_GLO_DEF.xsd  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]crea la carpeta del proyecto y los archivos en el  **\<unidad >: \Tutorial\BTAHL7V22Common\BTAHL72XCommon** carpeta.  
  
 Continúe con [paso 3: asignar un nombre seguro al ensamblado](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)