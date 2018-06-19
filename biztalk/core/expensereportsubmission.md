---
title: ExpenseReportSubmission | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
ms.assetid: d0bacab3-7092-44b8-a1c6-6f574a2db8bd
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c450e2e39f2498722f9eb8d09430294927cb05f8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969770"
---
# <a name="expensereportsubmission"></a>ExpenseReportSubmission
El ejemplo ExpenseReportSubmission indica cómo enviar un documento a una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde una aplicación cliente enriquecida como Microsoft Excel.  
  
 Las aplicaciones cliente enriquecidas le permiten realizar una serie de acciones, como la validación de datos y cálculos previos, en el equipo cliente. Esto ayuda a minimizar las interacciones con el servidor de servicios de fondo, lo que puede resultar útil cuando solo hay disponibles conexiones con poco ancho de banda.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe asegurarse de que el entorno de desarrollo está configurado y habilitado para funcionar con los servicios web de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [habilitar servicios Web](../core/enabling-web-services.md).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo indica cómo enviar un informe de gastos a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directamente desde Excel, mediante la siguiente secuencia de pasos:  
  
1.  El usuario realiza los pasos manuales del ejemplo que se proporcionan en la hoja de cálculo de Excel.  
  
2.  El código de macros de la hoja de cálculo convierte los datos de ésta en formato de Lenguaje de marcado extensible (XML) y, mediante una conexión HTTP, envía el mensaje XML a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
3.  El equipo que está ejecutando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recupera el mensaje de informe de gastos XML, valida su formato usando el esquema proporcionado y lo coloca en una carpeta distinta.  
  
4.  En la práctica, más allá del alcance de este ejemplo, otra aplicación como, por ejemplo, un sistema de planeamiento de recursos empresariales (ERP) recuperaría el archivo de la hoja de cálculo para un procesamiento posterior.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de ruta de acceso*\>\AdaptersUsage\ExpenseReportSubmission\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Cleanup.bat|Anula la implementación de ensamblados y los elimina de la caché de ensamblados global (GAC); elimina puertos de envío y de recepción; elimina directorios virtuales de los Servicios de Microsoft Internet Information Server (IIS) según sea necesario.|  
|ExpenseReport.15.3.xls|Hoja de cálculo de Excel con el diseño de informe de gastos, macros asociadas y botones para invocar las macros.|  
|MessageExample.xml|Ejemplo de formato de informe de gastos XML.|  
|Setup.bat|Crea e inicializa este ejemplo.|  
|En la carpeta \BTSExpenseDemo:<br /><br /> AssemblyInfo.cs,<br /><br /> BTSExpenseDemo.btproj,<br /><br /> BTSExpenseDemo.sln|Proporciona archivos de proyectos, de soluciones y archivos relacionados para este ejemplo.|  
|En la carpeta \BTSExpenseDemo:<br /><br /> BTSExpenseDemoBinding.xml|Se utiliza para la instalación automatizada, como el enlace de puertos.|  
|En la carpeta \BTSExpenseDemo:<br /><br /> BTSExpenseOrchestration.odx|Proporciona una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para este ejemplo.|  
|En la carpeta \BTSExpenseDemo:<br /><br /> SchemaExpenseReport.xsd|Proporciona un esquema para el formato de informe de gastos XML.|  
  
### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\AdaptersUsage\ExpenseReportSubmission  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Compila el proyecto de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo e implementa el ensamblado resultante.  
  
    -   Crea y enlaza los puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
        > [!NOTE]
        >  Este ejemplo muestra las siguientes advertencias al crear y enlazar los puertos:  
        >   
        >  `Warning: Receive handler not specified for receive location "BTSExpenseReceiveLocation"; updating with first receive handler with matching transport type.`  
        >   
        >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.BTSExpenseDemo.BTSOrchestration"; updating with first available host`.  
        >   
        >  Puede omitir estas advertencias de forma segura. (Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).  
  
    -   Habilita la ubicación de recepción e inicia el puerto de envío.  
  
    -   Configura IIS.  
  
    -   Enlaza e inicia la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    -   Establece la dirección HTTP para la ubicación que espera la hoja de cálculo de Excel.  
  
    > [!NOTE]
    >  Para obtener más información sobre el filtro ISAPI de BizTalk, consulte [cómo configurar IIS para una ubicación de recepción HTTP](../core/how-to-configure-iis-for-an-http-receive-location.md).  
  
    > [!NOTE]
    >  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
    > [!NOTE]
    >  Si selecciona abrir y crear el proyecto de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la Utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar el ensamblado resultante.  
  
    > [!NOTE]
    >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
3.  El archivo setup.bat configura el directorio virtual de este ejemplo para ejecutarlo en el grupo de aplicaciones de IIS asociado al sitio Web predeterminado.  Para configurar el directorio virtual para este ejemplo y ejecutarlo en el contexto de un usuario en el **usuarios de hosts aislados de BizTalk** y **IIS_WPG** grupos de usuarios, debe configurar el directorio virtual para ejecutarlo en una nueva Grupo de aplicaciones de IIS.  Configure el directorio virtual para ejecutarlo en un grupo de aplicaciones IIS nuevo realizando los pasos que se indican a continuación:  
  
    > [!NOTE]
    >  Si ya ha creado un grupo de aplicaciones nuevo para otro ejemplo de SDK, puede continuar con el último punto que aparece más abajo.  
  
    1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
    2.  En el **Internet Information Services (IIS) Manager**, navegue hasta la **grupos de aplicaciones** carpeta.  
  
    3.  Haga clic en el **grupos de aplicaciones** carpeta y haga clic en **New**, **grupo de aplicaciones...**  
  
    4.  Escriba un nombre para el **Id. de grupo de aplicaciones:** como BizTalkSDKSamples, compruebe que la **usar configuración predeterminada para el nuevo grupo de aplicaciones** opción está seleccionada y haga clic en **Aceptar** a Crear nuevo grupo de aplicaciones.  
  
    5.  Haga clic en el nuevo grupo de aplicaciones y, a continuación, haga clic en **propiedades**.  
  
    6.  Haga clic en el **identidad** ficha del cuadro de diálogo Propiedades del cuadro y cambiar la identidad bajo la que se ejecuta este grupo de aplicaciones a un usuario que sea miembro de la **usuarios de hosts aislados de BizTalk** grupo de usuarios.  Este usuario también debe ser miembro de la variable local **IIS_WPG** grupo de usuarios.  
  
    7.  Configure el directorio virtual de este ejemplo SDK para ejecutarlo en el grupo de aplicaciones nuevo. El **grupo de aplicaciones:** está disponible en la **directorio Virtual** ficha del cuadro de diálogo de propiedades de directorio Virtual. El directorio virtual creado para este ejemplo es **ExpenseReportSubmission**.  
  
4.  Agregue una extensión de servicio Web a IIS para HTTPReceive.dll  
  
    1.  En el **Internet Information Services (IIS) Manager**, navegue hasta la **extensiones de servicio Web** carpeta.  
  
    2.  Haga clic en el **extensiones de servicio Web** carpeta y seleccione **agregar una nueva extensión de servicio Web** para mostrar la **nueva extensión de servicio Web** cuadro de diálogo.  
  
    3.  Escriba **ExpenseReportSubmission** para **nombre de la extensión:**  
  
    4.  Haga clic en **agregar** para mostrar la **Agregar archivo** cuadro de diálogo.  
  
    5.  Haga clic en **examinar** para mostrar la **abiertos** diálogo cuadro y vaya a  *\<carpeta de instalación de BizTalk Server\>* \HttpReceive\ BTSHTTPReceive.dll y haga clic en **abiertos**, a continuación, haga clic en **Aceptar**.  
  
    6.  Habilitar la opción de **establecer el estado de extensión a permitido** y haga clic en **Aceptar**.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo ExpenseReportSubmission.  
  
> [!NOTE]
>  Si está utilizando las características de seguridad mejorada de Microsoft Excel, es posible que las macros estén deshabilitadas en la hoja de cálculo. Siga las instrucciones proporcionadas por Excel sobre cómo ejecutar macros no asignadas desde una fuente confiable.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra el archivo de Excel ExpenseReport.15.3.xls que se incluye con este ejemplo.  
  
2.  Si lo desea, cambie los datos del ejemplo en la hoja de cálculo sin cambiar su formato.  
  
3.  En la hoja de cálculo, haga clic en **iniciar** para realizar cálculos locales.  
  
     El texto del botón cambia de **iniciar** a **enviar**.  
  
4.  En la hoja de cálculo, haga clic en **enviar**.  
  
5.  Observe el texto del mensaje enviado, el resultado en la parte superior de la tabla con el fondo amarillo (celda C7) y el código devuelto y la descripción de texto en la parte inferior y a la derecha (celda G23).  
  
     Si el envío no se produce correctamente, vuelva a intentarlo. Además, vea la tabla de solución de problemas que aparece en la sección Comentarios.  
  
## <a name="comments"></a>Comentarios  
 Escenarios como éste se pueden dar cuando, por ejemplo, un equipo de ventas de campo está equipado con versiones anteriores de Microsoft Windows que no admiten .NET Framework y para el que no es viable el requisito de actualizar a una versión más actual.  
  
 Las características esenciales que se muestran en este ejemplo son las siguientes:  
  
-   Envío desde una aplicación cliente enriquecida (que no esté basada en .NET)  
  
-   Integración de Microsoft Office  
  
-   Conexiones de recepción HTTP  
  
-   Orquestaciones sencillas  
  
-   Adaptador de archivo  
  
 En la siguiente tabla se muestran algunos posibles errores de envío y sus soluciones.  
  
|Código de error HTTP|Acciones posibles|  
|---------------------|---------------------|  
|401 No autorizado|Habilitar el acceso anónimo al directorio virtual.|  
|503 Servicio no disponible y la mayoría del resto de códigos HTTP en los rangos 400 y 500|Asegurarse de que se ejecuta el host y de que se ha implementado el servicio, está enlazado al puerto correcto y se ha iniciado.|  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores: uso](../core/adapter-samples-usage.md)