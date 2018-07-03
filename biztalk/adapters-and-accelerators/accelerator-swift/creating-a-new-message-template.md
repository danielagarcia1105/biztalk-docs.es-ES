---
title: Crear una nueva plantilla de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, templates
- templates, creating
- creating, templates
ms.assetid: 8c601d2b-b7a5-4ac4-9d98-fd9960038340
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e89c34b29818ab053217b823c6f8a787ce50a15d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999837"
---
# <a name="creating-a-new-message-template"></a>Crear una nueva plantilla de mensaje
Puede crear una nueva plantilla de mensaje de una plantilla existente. Esto permite un creador crear una nueva instancia de mensaje en un formulario personalizado, como una copia de un formulario estándar SWIFT que ya tiene algunos datos introducidos en él. Con la nueva plantilla, el creador no tiene que todos los valores de los datos necesarios para utilizar un formulario vacío especificar.  
  
 Crear una nueva plantilla de una instancia de mensaje que ha generado mediante la plantilla existente correspondiente. Agregar datos a los campos de la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forma (como si estuviera creando una nueva instancia de mensaje) y, a continuación, guarde el formulario como una nueva plantilla.  
  
### <a name="to-save-a-modified-existing-template-as-a-new-template"></a>Para guardar una plantilla existente modificada como una nueva plantilla  
  
1. En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.  
  
2. Haga clic en **Documentos**.  
  
3. En la página de documentos, haga clic en el **nuevos mensajes de SWIFT MT** biblioteca de documentos.  
  
4. En la página nuevos mensajes de SWIFT MT, haga clic en la categoría que contiene la plantilla que desea basar la nueva plantilla.  
  
5. Elija la plantilla que desea basar la nueva plantilla, haga clic en la flecha situada a la derecha y, a continuación, haga clic en **editar en Microsoft Office InfoPath**.  
  
6. En el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana, en el formulario de mensaje, escriba los datos de mensaje que se van a formar parte de la plantilla.  
  
7. Haga clic en **archivo**y, a continuación, haga clic en **Guardar como**.  
  
8. En el menú emergente que indica que el formulario contiene errores de validación, haga clic en **Sí**.  
  
9. En el cuadro de diálogo Guardar como, seleccione la carpeta para la plantilla en el **guardar en** texto cuadro y, a continuación, escriba un nombre de archivo en el **nombre de archivo** cuadro de texto. Haga clic en **Guardar**.  
  
10. Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario para la nueva plantilla.  
  
    > [!NOTE]
    >  Para crear una instancia de mensaje de la nueva plantilla, consulte [crear y enviar un mensaje nuevo](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md).