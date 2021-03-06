---
title: Implementación de esquemas de A4SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, A4SWIFT
- deploying, A4SWIFT schemas
- A4SWIFT, deploying schemas
- schemas, deploying
ms.assetid: a6aed2cd-3578-442e-ab1e-8284cc5f7b72
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8382141993d214ffbfc79a0a4eec3f2c06b4e456
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966365"
---
# <a name="deploying-a4swift-schemas"></a>Implementación de esquemas de A4SWIFT
Debe implementar los esquemas para los mensajes SWIFT que desea intercambiar.  
  
 **Resumen**  
  
 Implemente los siguientes esquemas:  
  
-   SWIFT Types.xsd Base  
  
-   SWIFT Types.xsd datos comunes  
  
-   Esquema específico para un tipo de mensaje, por ejemplo, MT103.xsd  
  
### <a name="to-create-a-strong-named-swift-project"></a>Para crear un proyecto SWIFT con nombre seguro  
  
1. En Visual Studio, haga clic en **archivo**, apunte a **New**y, a continuación, haga clic en **proyecto**.  
  
2. En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** panel, seleccione el **proyectos de BizTalk** carpeta.  
  
3. En el **plantillas** panel, seleccione **proyecto vacío de servidor BizTalk**.  
  
4. En el **nombre** , escriba el nombre que desee para el nombre del proyecto.  
  
5. En el **solución** cuadro, seleccione **crear nueva solución**. En el **ubicación** , escriba la ubicación del proyecto que se va a agregar a proyecto de esquema.  
  
6. Haga clic en **Aceptar** para abrir el nuevo proyecto.  
   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Agrega un nuevo proyecto en el Explorador de soluciones y crea la carpeta de proyecto y archivos en la carpeta especificada.  
  
7. Inicie el símbolo del sistema de Visual Studio.  
  
8. En el símbolo del sistema de Visual Studio, vaya a  **\< *unidad*\>: Acelerador de BizTalk para SWIFT \Program Files\Microsoft**.  
  
9. En el símbolo del sistema, escriba **sn – k key.snk**, y, a continuación, presione ENTRAR. Asegúrese de que se muestra un mensaje en la ventana de símbolo del sistema que indica que se ha escrito un par de claves a key.snk.  
  
10. En el Explorador de soluciones, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades**.  
  
11. En el panel izquierdo de la **páginas de propiedades** cuadro de diálogo, haga clic en **ensamblado**.  
  
12. En el panel derecho de la **páginas de propiedades** cuadro de diálogo, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
13. En el **archivo clave de ensamblado** cuadro de diálogo, vaya a  **\< *unidad*\>: \Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)], haga clic en **key.snk**y, a continuación, haga clic en **abierto**.  
  
14. En el **páginas de propiedades** cuadro de diálogo, haga clic en **Aceptar** para guardar los cambios.  
  
### <a name="to-add-a-swift-schema"></a>Para agregar un esquema SWIFT  
  
1.  En el Explorador de soluciones de Visual Studio, abra el proyecto.  
  
2.  Haga clic en el proyecto, elija **agregar**y, a continuación, haga clic en **elemento existente**.  
  
3.  En el **Agregar elemento existente** cuadro de diálogo el:\\**programa Files\Microsoft BizTalk Accelerator para SWIFT \<versión\> Messages\A4SWIFT SRG mensaje Pack\SWIFT\<versión\>\Base esquemas**. Seleccione el **SWIFT Base Types.xsd** y **Types.xsd datos comunes de SWIFT** esquemas y, a continuación, haga clic en **agregar**.  
  
4.  Haga clic en el proyecto, elija **agregar**y, a continuación, haga clic en **Agregar elemento existente**.  
  
5.  En el **Agregar elemento existente** cuadro de diálogo el **buscar en** cuadro desplegable, desplácese a  **\<unidad\>: Acelerador de BizTalk para SWIFT \ProgramFiles\Microsoft\<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category n\MTxxx**. Seleccionar un esquema para un tipo de mensaje, por ejemplo **MT103.xsd**y, a continuación, haga clic en **agregar**.  
  
    > [!NOTE]
    >  A4SWIFT agrega el esquema para el proyecto, como se muestra en el Explorador de soluciones.  
  
6.  En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Versión de compilación**.  
  
7.  En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Implementar**.