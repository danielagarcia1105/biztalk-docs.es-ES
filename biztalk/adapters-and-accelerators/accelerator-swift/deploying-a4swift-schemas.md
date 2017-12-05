---
title: "Implementación de esquemas de A4SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, A4SWIFT
- deploying, A4SWIFT schemas
- A4SWIFT, deploying schemas
- schemas, deploying
ms.assetid: a6aed2cd-3578-442e-ab1e-8284cc5f7b72
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc89b26d0eee970268d5e9084cd0827d3100fd7b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="deploying-a4swift-schemas"></a>Implementación de esquemas de A4SWIFT
Debe implementar los esquemas para los mensajes SWIFT que desea intercambiar.  
  
 **Resumen**  
  
 Implementar los siguientes esquemas:  
  
-   SWIFT Types.xsd Base  
  
-   SWIFT Types.xsd datos comunes  
  
-   Esquema específico para un tipo de mensaje, por ejemplo, MT103.xsd  
  
### <a name="to-create-a-strong-named-swift-project"></a>Para crear un proyecto SWIFT con nombre seguro  
  
1.  En Visual Studio, haga clic en **archivo**, seleccione **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** panel, seleccione la **proyectos de BizTalk** carpeta.  
  
3.  En el **plantillas** panel, seleccione **proyecto vacío de servidor BizTalk**.  
  
4.  En el **nombre** , escriba el nombre que desea para el nombre del proyecto.  
  
5.  En el **solución** cuadro, seleccione **crear nueva solución**. En el **ubicación** cuadro, escriba la ubicación del proyecto que se va a agregar el proyecto de esquema.  
  
6.  Haga clic en **Aceptar** para abrir el nuevo proyecto.  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]Agrega un nuevo proyecto en el Explorador de soluciones y crea la carpeta del proyecto y los archivos en la carpeta especificada.  
  
7.  Inicie el símbolo del sistema de Visual Studio.  
  
8.  En el símbolo del sistema de Visual Studio, vaya a  **\<* unidad*\>: \Program Acelerador de BizTalk para SWIFT **.  
  
9. En el símbolo del sistema, escriba **sn – k key.snk**, y, a continuación, presione ENTRAR. Asegúrese de que se muestra un mensaje en la ventana de símbolo del sistema que indica que se ha escrito un par de claves para key.snk.  
  
10. En el Explorador de soluciones, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades**.  
  
11. En el panel izquierdo de la **páginas de propiedades** cuadro de diálogo, haga clic en **ensamblado**.  
  
12. En el panel derecho de la **páginas de propiedades** cuadro de diálogo, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo de clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
13. En el **archivo de clave de ensamblado** cuadro de diálogo, vaya a  **\<* unidad*\>: \Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)], haga clic en **key.snk**y, a continuación, haga clic en **abiertos**.  
  
14. En el **páginas de propiedades** cuadro de diálogo, haga clic en **Aceptar** para guardar los cambios.  
  
### <a name="to-add-a-swift-schema"></a>Para agregar un esquema SWIFT  
  
1.  En el Explorador de soluciones de Visual Studio, abra el proyecto.  
  
2.  Haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.  
  
3.  En el **Agregar elemento existente** cuadro de diálogo el:\\**programa Files\Microsoft BizTalk Accelerator para SWIFT \<versión\> Pack\SWIFT Messages\A4SWIFT-SRGdemensaje\<versión\>\Base esquemas**. Seleccione el **SWIFT Base Types.xsd** y **Types.xsd de datos común de SWIFT** esquemas y, a continuación, haga clic en **agregar**.  
  
4.  Haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **Agregar elemento existente**.  
  
5.  En el **Agregar elemento existente** cuadro de diálogo, en la **buscar en** cuadro de lista desplegable, desplácese a  **\<unidad\>: \Program Acelerador de BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category n\MTxxx**. Seleccionar un esquema para un tipo de mensaje, por ejemplo **MT103.xsd**y, a continuación, haga clic en **agregar**.  
  
    > [!NOTE]
    >  A4SWIFT agrega el esquema para el proyecto, como se muestra en el Explorador de soluciones.  
  
6.  En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Versión de compilación**.  
  
7.  En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Implementar**.