---
title: Crear e implementar canalizaciones de A4SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- deploying, pipelines
- pipelines, deploying
- pipelines, creating
ms.assetid: 2a614510-7e15-4e88-9012-fc019d3aefee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d337b97dfb1973ef10c113ae0a206a51dcd63b1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002453"
---
# <a name="creating-and-deploying-a4swift-pipelines"></a>Crear e implementar canalizaciones de A4SWIFT
Realice los pasos siguientes para crear e implementar canalizaciones SWIFT para reparación de mensajes y nuevo envío, tal como se muestra en la ilustración siguiente.  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")  

 **Resumen**  

 Implemente los siguientes esquemas:  

-   Canalización con el Desensamblador de SWIFT de recepción personalizada. Establecer propiedades de validación de XML y la validación del BRE en True y la propiedad de esquema de encabezado de SWIFT en (None).  

-   Canalización con el ensamblador de SWIFT de envío personalizada  

### <a name="to-create-a-pipeline-project"></a>Para crear un proyecto de canalización  

1. En Visual Studio, haga clic en **archivo**, apunte a **New**y, a continuación, haga clic en **proyecto**.  

2. En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** panel, seleccione el **proyectos de BizTalk** carpeta.  

3. En el **plantillas** panel, seleccione **proyecto vacío de servidor BizTalk**.  

4. En el **nombre** , escriba el nombre que desee para el nombre del proyecto.  

5. En el **solución** cuadro, seleccione **agregar a solución**. En el **ubicación** , escriba la ubicación del proyecto de esquema que ha creado en [implementar esquemas de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).  

6. Haga clic en **Aceptar** para abrir el nuevo proyecto.  
   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Agrega un nuevo proyecto en el Explorador de soluciones y crea la carpeta de proyecto y archivos en la carpeta especificada.  

7. Crear y asignar un archivo de clave seguro al proyecto. Para obtener más información, vea "para crear un proyecto SWIFT con nombre seguro" en [implementar esquemas de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).  

### <a name="to-add-a-custom-receive-pipeline"></a>Para agregar una canalización de recepción personalizada  

1. En el Explorador de soluciones, haga clic en el proyecto de canalización, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  

2. En el cuadro de diálogo Agregar nuevo elemento, haga clic en **archivos de canalización** en el panel de categorías y, a continuación, seleccione **canalización de recepción** desde el panel Plantillas.  

3. En el **nombre** , escriba un nombre para la canalización.  

4. Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.  

5. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, **cuadro de herramientas**.  

6. Desde el **cuadro de herramientas de componentes de canalización de BizTalk**, arrastre el **Desensamblador de SWIFT** a la **Coloque aquí** cuadro a continuación el **desensamblar** fase en la forma **Diseñador de canalizaciones de BizTalk**. Deje el **Desensamblador de SWIFT** seleccionado en el **Diseñador de canalizaciones de BizTalk**.  

7. En **propiedades**, compruebe que la **BRE validación** y **validación XML** propiedades se establecen en **True**.  

   > [!NOTE]
   >  Debe establecerse la propiedad de esquema de encabezado de SWIFT **(ninguno)**.  

8. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **archivo**y, a continuación, **guardar todo**.  

### <a name="to-add-a-custom-send-pipeline"></a>Para agregar una canalización de envío personalizada  

1. En el Explorador de soluciones, haga clic en el **SWIFTPipelines** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  

2. En el cuadro de diálogo Agregar nuevo elemento, compruebe que **archivos de canalización** está seleccionado en el panel de categorías y, a continuación, seleccione **canalización de envío** desde el panel Plantillas.  

3. En el **nombre** , escriba un nombre para la canalización.  

4. Haga clic en **agregar** para abrir la canalización en blanco en el Diseñador de canalizaciones de BizTalk.  

   > [!NOTE]
   >  Una canalización vacía aparece en el Diseñador de canalizaciones de BizTalk. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Agrega la nueva canalización al explorador de soluciones bajo el proyecto SWIFTPipelines.  

5. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, **cuadro de herramientas**.  

6. En el **cuadro de herramientas de componentes de canalización de BizTalk**, arrastre **ensamblador de SWIFT** a la **Coloque aquí** cuadro a continuación el **ensamblar** en forma de fase **Diseñador de canalizaciones de BizTalk**.  

7. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **archivo**y, a continuación, **guardar todo**.  

8. A la derecha, haga clic en el proyecto de canalizaciones y, a continuación, haga clic en **compilar**.  

   > [!NOTE]
   >  Durante el proceso de compilación, no debería ver los errores. Si lo hace, comprobar el origen del error, corríjalo y, a continuación, volver a compilar el proyecto. Sin embargo, es posible que, verá advertencias. Puede corregir la condición que conduce a las advertencias. Para obtener más información, vea "Creación de un proyecto de canalización podrían producir advertencias de" en [varios problemas conocidos](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).  

9. A la derecha, haga clic en el proyecto de canalizaciones y, a continuación, haga clic en **implementar**.
