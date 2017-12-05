---
title: 'Paso 2: Crear Fabrikam LOBWebApplication | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOBWebApplication
- LOBWebApplication
ms.assetid: 2ff8bd20-7fbc-4e16-b177-bb4afac7f7c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0732322d663e51c27bbaab957caa5474cc685326
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-creating-the-fabrikam-lobwebapplication"></a>Paso 2: Crear el Fabrikam LOBWebApplication
En este paso, creará la aplicación de LOB que Fabrikam usa para enviar una solicitud PIP 3A2 a Contoso. El proyecto LOBWebApplication está instalado en el [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK. Para ejecutar la aplicación Web, tendrá que crear un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] directorio virtual de Internet Information Services (IIS) y compile el proyecto LOBWebApplication.  
  
> [!NOTE]
>  Si completó el tutorial de DoubleAction, no es necesario realizar este paso.  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a>Para crear el directorio virtual LOBWebApplication  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services**.  
  
    > [!NOTE]
    >  Si ya ha hecho el tutorial de doble acción, ya habrá creado el directorio virtual LOBWebApplication para este tutorial. Si es así, no es necesario llevar a cabo estos pasos. Sin embargo, tendrá que cambiar los permisos para el directorio virtual de **ejecutar secuencias de comandos** a **lectura**.  
  
2.  En el Administrador de Internet Information Services, expanda **< nombre_equipo > (equipo local)**y, a continuación, expanda **sitios Web**.  
  
3.  Haga clic con el botón secundario en **Sitio Web predeterminado**, elija **Nuevo**y, a continuación, haga clic en **Directorio virtual**.  
  
4.  En el **Welcometo la página del Asistente para crear un directorio Virtual**, haga clic en **siguiente**.  
  
5.  En la página **Alias del directorio virtual** , en el cuadro **Alias** , escriba **LOBWebApplication**y, a continuación, haga clic en **Siguiente**.  
  
6.  En el **directorio de contenido del sitio Web** página, haga clic en **examinar**, seleccione la  **\<unidad\>: \Program BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication** carpeta y, a continuación, haga clic en **Aceptar**. Haga clic en **Siguiente**.  
  
7.  En el **permisos de acceso de directorio Virtual** página, haga clic en **siguiente**.  
  
8.  Haga clic en **finalizar** para crear el directorio virtual.  
  
### <a name="excluding-lobwebapplication-from-sharepoint"></a>Exclusión de LOBWebApplication de SharePoint  
  
1.  Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administración central de SharePoint**.  
  
    > [!NOTE]
    >  Si ya ha hecho el tutorial de doble acción, que ya habrá excluido el directorio virtual LOBWebApplication de SharePoint para este tutorial. Si es así, no es necesario llevar a cabo estos pasos.  
  
2.  En el **Administración Central** página, en la **configuración del servidor Virtual** sección, seleccione **extender o actualizar el servidor virtual**.  
  
3.  Si no ve la dirección URL configurada en el equipo, haga clic en **Lista completa**.  
  
4.  Seleccione **sitio Web predeterminado**.  
  
5.  En la sección **Administración del servidor virtual** , haga clic en **Definir rutas de acceso administradas**.  
  
6.  En el **agregar nueva ruta de acceso** sección, en la **ruta de acceso** , escriba "/ LOBWebApplication". En **Tipo**, seleccione **Ruta excluida**y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-build-the-lobwebapplication-project"></a>Para compilar el proyecto LOBWebApplication  
  
1.  Inicie **Microsoft Visual Studio 2012**.  
  
2.  Desde el **archivo** menú, elija **abiertos**y, a continuación, haga clic en **Project\Solution**.  
  
3.  En el cuadro de diálogo Abrir proyecto, en **buscar en**, mover a  **\<unidad\>: \Program BizTalk \<versión\> Acelerador para RosettaNet\ SDK\ LOBWebApplication**, seleccione la **LOBWebApplication.sln** solución y, a continuación, haga clic en **abiertos**.  
  
4.  En el Explorador de soluciones, haga clic en el nodo superior (http://localhost/LOBWebApplication) y, a continuación, haga clic en **Agregar referencia**.  
  
5.  En el cuadro de diálogo Agregar referencia, haga clic en **examinar** y mover a  **\<unidad\>: \Program BizTalk \<versión\> Accelerator for RosettaNet\bin** .  
  
6.  **Seleccione el Microsoft.Solutions.BTARN.ConfigurationManager.dll y Microsoft.Solutions.BTARN.Shared.dll** ensamblados **y, a continuación, haga clic en Aceptar.**  
  
7.  En el **generar** menú, haga clic en **Generar sitio Web**.  
  
### <a name="to-run-the-lobwebapplication-project"></a>Para ejecutar el proyecto LOBWebApplication  
  
1.  En el Explorador de soluciones, haga clic en **default.aspx**y, a continuación, seleccione **establecer como página principal**.  
  
2.  En el **depurar** menú, haga clic en **iniciar sin depurar**.  
  
## <a name="see-also"></a>Vea también  
 [Probar la solución](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)