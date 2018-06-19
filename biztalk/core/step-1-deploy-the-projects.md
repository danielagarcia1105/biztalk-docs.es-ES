---
title: 'Paso 1: Implementar los proyectos | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0467c140-1f4c-4cfa-b46f-dc1d0f8755d4
caps.latest.revision: 44
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad4424327f6cd24624abe6b4a850f3c24153e6a4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974130"
---
# <a name="step-1-deploy-the-projects"></a>Paso 1: Implementar los proyectos
![Paso 1 de 3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, se implementarán los proyectos EAISchemas y EAIOrchestration.  
  
 **Propósito:** al implementar un proyecto o solución en Visual Studio, los ensamblados automáticamente compilados e implementados en la aplicación especificada. Como parte de este proceso, el ensamblado junto con las orquestaciones, esquemas y asignaciones que contiene (denominados "artefactos") se importan a la base de datos de administración de BizTalk local y se asocian en ella con la aplicación especificada.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   [Lección 1: Definir los esquemas y una asignación](../core/lesson-1-define-schemas-and-a-map.md)  
  
-   [Lección 2: Definir el proceso empresarial](../core/lesson-2-define-the-business-process.md)  
  
-   Inicie sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores

-   Ejecutar Visual Studio con privilegios de administrador

> [!TIP]
> Puede descargar los archivos del tutorial necesarios en [Tutorial 1: integración de aplicaciones empresariales](https://www.microsoft.com/download/details.aspx?id=22793).

## <a name="open-the-solution-with-administrative-rights"></a>Abra la solución con derechos administrativos  
  
1.  Inicie sesión como miembro del grupo Administradores de BizTalk Server en Windows.  
  
2.  Iniciar **Microsoft Visual Studio** como administrador.  
  
3.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **abiertos**y, a continuación, haga clic en **proyecto/solución**.  
  
4.  En el **Abrir proyecto** cuadro de diálogo, vaya a la **EAISolution.sln** archivo de solución del proyecto y, a continuación, haga clic en **abiertos**.  
  
 El proceso de implementación necesita que el ensamblado esté firmado de forma segura.  Debe firmar los ensamblados asociando el proyecto con un archivo de clave de ensamblado de nombre seguro.  Este archivo se incluye en los archivos del tutorial.  
  
 La aplicación de BizTalk es una característica de BizTalk Server que facilita y agiliza la implementación, administración y solución de problemas de las soluciones empresariales de BizTalk Server. Una aplicación de BizTalk es una agrupación lógica de elementos, denominados "artefactos", que se utiliza en una solución empresarial de BizTalk Server. Se puede especificar un nombre de aplicación para un proyecto.  El proceso de implementación crea automáticamente una nueva aplicación con el nombre especificado, si no existe.  
  
## <a name="configure-and-deploy-the-projects"></a>Configurar e implementar los proyectos  
  
1.  En el Explorador de soluciones, haga clic en el **EAISchemas** del proyecto y, a continuación, haga clic en **propiedades**.  
  
2.  Haga clic en el **firma** ficha, seleccione **firmar el ensamblado**.  
  
3.  En la lista desplegable de la **elegir un archivo de clave de nombre seguro** cuadro, seleccione  **\<Examinar... \>**.  
  
4.  En el **Seleccionar archivo** diálogo cuadro, vaya a **C:\BTStutorials**, haga clic en **tutorials.snk**y, a continuación, haga clic en **abiertos**. 
  
5.  Haga clic en el **implementación** ficha, en el cuadro a la derecha del **nombre de la aplicación**, tipo `EAISolution`.  
  
6.  En la lista desplegable en el cuadro a la derecha del **volver a implementar**, seleccione **True**.  
  
7.  En el Explorador de soluciones, haga clic en **EAISchemas**y, a continuación, haga clic en **implementar**.  En la ventana de salida se debe ver:  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  Repita los pasos del 1 al 7 para implementar el proyecto EAIOrchestration.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha implementado los proyectos EAISchemas y EAIOrchestration.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Debe crear los puertos físicos y enlazarlos a los puertos lógicos de la orquestación.  
  
 [Paso 2: Configurar e iniciar la aplicación](../core/step-2-configure-and-start-the-application1.md)   
 [Paso 3: Probar la solución](../core/step-3-test-the-solution2.md)
