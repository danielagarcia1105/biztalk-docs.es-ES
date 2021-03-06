---
title: 'Paso 1: Crear el proyecto EAISchemas | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a14ee61-fa27-4f03-997e-42c34a77afee
caps.latest.revision: 55
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb51c936edfcc20009048abcb90bb8ead72fd11c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974461"
---
# <a name="step-1-create-eaischemas-project"></a>Paso 1: Crear el proyecto EAISchemas
![Paso 1 de 5](../core/media/step-1of5.gif "Step_1of5")  

 **Tiempo en completarse:** 5 minutos  

 **Objetivo:** en este paso, creará un nuevo [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solución y un proyecto.  

 **Propósito:** usar el sistema de proyectos de BizTalk para crear parte o todo un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] aplicación o solución empresarial. El elemento principal de una solución de este tipo es un proyecto de BizTalk, es decir, una colección de elementos como, por ejemplo, esquemas, orquestaciones, tipos de mensajes Web, clases, canalizaciones, asignaciones y referencias, que se pueden crear y generar en un ensamblado antes de implementarlo.  

## <a name="prerequisites"></a>Requisitos previos  
 Tenga en cuenta los siguientes requisitos antes de iniciar este paso:  

-   Antes de comenzar este paso debe completar los pasos descritos en [antes de comenzar el Tutorial](../core/before-you-begin-the-tutorial.md).  

## <a name="procedures"></a>Procedimientos  

#### <a name="to-create-a-new-visual-studio-solutionproject"></a>Para crear un nuevo proyecto/solución de Visual Studio  

1. Iniciar **Microsoft Visual Studio**.  

2. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  

3. En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  


   |             Use              |                                Para                                |
   |-----------------------------------|--------------------------------------------------------------------------|
   |      **Plantillas instaladas**      | Haga clic en **proyectos de BizTalk**, a continuación, haga clic en **proyecto vacío de servidor BizTalk**. |
   |             **Nombre**              |                           Tipo **EAISchemas**.                           |
   |           **Ubicación**            |                      Tipo **C:\tutorial\Lessons**.                       |
   |         **Nombre de solución**         |                          Tipo **EAISolution**.                           |
   | **Crear directorio para la solución** |                                (se selecciona)                                |


4. Haga clic en **Aceptar**.  

5. En el menú **Archivo** , haga clic en **Guardar todo**.  

## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, abrió un nuevo proyecto y una solución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  

## <a name="next-steps"></a>Pasos siguientes  
 Creará el esquema para el mensaje de solicitud de reposición de inventario.  

## <a name="see-also"></a>Vea también  
 [Antes de comenzar el Tutorial](../core/before-you-begin-the-tutorial.md)   
 [Paso 2: Crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md)   
 [Paso 3: Crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md)   
 [Paso 4: Crear el mapa](../core/step-4-create-the-map.md)   
 [Paso 5: Generar el proyecto EAISchemas](../core/step-5-build-the-eaischemas-project.md)   
 [Herramientas de desarrollo](../core/developer-tools.md)   
 [Trabajar con proyectos de BizTalk](../core/working-with-biztalk-projects.md)