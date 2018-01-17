---
title: "Implementación de esquemas de sobres de A4SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, envelope schemas
- A4SWIFT, deploying envelope schemas
- envelope schemas
- schemas, envelope schemas
ms.assetid: 6440608c-d30d-4d82-827a-8a4b2738db85
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8811f1dd056ca5a4ea4582d593af30e2ffc879f
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="deploying-a4swift-envelope-schemas"></a>Implementación de esquemas de sobres de A4SWIFT
Debe incluir esquemas de sobres en proyectos de esquema siempre que se establezca una reparación de mensajes y nuevo envío. Un esquema de sobre, por ejemplo, EnvelopeMT103.xsd, es necesario para escribir en el sitio de MRSR.  
  
 **Resumen**  
  
 Agregar esquemas de sobres a su proyecto, como se indica a continuación:  
  
-   En Visual Studio, en el proyecto que contiene los esquemas de mensaje, agregue un esquema de sobre para cada esquema de mensaje.  
  
-   Agregar una referencia a RuntimeSchemas.dll a cualquier proyecto que contiene uno o varios esquemas de sobres.  
  
    > [!NOTE]
    >  Agregar una referencia a RuntimeSchemas.dll es necesario para un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] sólo cuando haya agregado un esquema de sobre de reparación de mensajes y nuevo envío al proyecto del proyecto.  
  
-   Agregue el esquema de sobre mensaje sin analizar (EnvelopeUnparsedMessage.xsd) al proyecto.  
  
### <a name="to-add-a-swift-envelope-schema"></a>Para agregar un esquema de sobre SWIFT  
  
1.  En el Explorador de soluciones de Visual Studio, abra el proyecto de esquemas.  
  
2.  Haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
3.  En el cuadro de diálogo Agregar referencia, haga clic en el **examinar** etiqueta.  
  
4.  En el cuadro de diálogo Seleccionar componente, abra el **buscar en** lista desplegable. Mover a ***\<unidad\>*:\Program de programa\Microsoft BizTalk Accelerator para SWIFT \<versión\> Pack\Assemblies mensaje**. Seleccione **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** en la lista de ensamblados y, a continuación, haga clic en **agregar**.  
  
5.  En el **Agregar referencia** cuadro de diálogo, haga clic en **Aceptar**.  
  
6.  Haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **Agregar elemento existente**.  
  
7.  En Agregar elemento existente cuadro de diálogo, en la **buscar en** cuadro de lista desplegable, desplácese a  **\<unidad\>: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\>Mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Categoryn\MTxxx**. Seleccione el esquema de sobres, por ejemplo, **EnvelopeMT103.xsd**y, a continuación, haga clic en **agregar**.  
  
     En Agregar elemento existente cuadro de diálogo, en la **buscar en** cuadro de lista desplegable, desplácese a. Seleccione el esquema de sobres, por ejemplo, EnvelopeMT103.xsd y, a continuación, haga clic en Agregar.  
  
    > [!NOTE]
    >  A4SWIFT agrega el esquema de sobre para el proyecto, como se muestra en el Explorador de soluciones.  
  
8.  En el Explorador de soluciones, haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **Agregar elemento existente**.  
  
9. Si utiliza la característica de reparación de mensajes y nuevo envío, en el cuadro de diálogo Agregar elemento existente, en la **buscar en** cuadro de lista desplegable, desplácese a  **\< *unidad*\>: \ Acelerador de Microsoft BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Unparsed mensaje**. Seleccione **EnvelopeUnparsedMessage.xsd**y, a continuación, haga clic en **agregar**.  
  
10. En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Versión de compilación**.  
  
11. En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Implementar**.