---
title: Loans Processing Using Business Rules (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 3e1c80c6-adc1-4a0f-83fd-409ce1b8f21f
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c51f0ff13b06bd57ccdd52ec6e35fdd7e0acf839
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="loans-processing-using-business-rules-biztalk-server-sample"></a>Préstamos procesamiento con reglas de negocios (ejemplo de BizTalk Server)
En el ejemplo Loans Processing Using Business Rules se muestra cómo usar un conjunto de reglas administrado en una orquestación y cómo usar una combinación de entradas conocidas como hechos para calcular la configuración de algunos campos en un documento que se está procesando. Los hechos pueden ser el resultado de la llamada a un ensamblado basado en .NET, de los valores recuperados del XML del mensaje o de los datos recuperados de una base de datos. En el ejemplo también se muestra cómo puede cambiar las reglas en cualquier momento, lo que afecta a los cálculos posteriores sin tener que volver a realizar la implementación.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo se muestran estas funciones en el contexto de un escenario de procesamiento de préstamos simplificado. La orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recoge y procesa una solicitud de préstamo, que se conoce también como un escenario de préstamo, en formato de mensaje XML. Esta orquestación usa el Motor de reglas de negocios para evaluar los mensajes entrantes en base a las reglas, modifica el mensaje con el resultado de la aplicación de las reglas y, a continuación, escribe el mensaje como un archivo en la carpeta de salida.  
  
 Basadas en hechos de varios orígenes, incluido el mensaje que se va a procesar, este ejemplo establece el **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**y  **ResidencyStatus** elementos del mensaje que se va a procesar.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de ruta de acceso*> \Business Rules\Loans Processing using Business Rules\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Case.xsd|Archivo de esquema para solicitudes de préstamos entrantes, que se conocen también como escenarios de préstamos.|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC). Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|Create_CustInfo_Table.sql|Secuencia de comandos de SQL para la creación de la tabla CustInfo en la base de datos de ejemplo Northwind de SQL.|  
|LoanProcessorBinding.xml|Se utiliza para la instalación automatizada, como el enlace de puerto.|  
|LoansProcessor.btproj, LoansProcessor.sln|Proyecto de BizTalk y archivos de solución para este ejemplo.|  
|My Sample Service.odx|Orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para este ejemplo.|  
|sampleLoan.xml|Archivo de entrada de ejemplo, con valores vacíos para los cuatro elementos de estado al final de la estructura XML en el archivo.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
|En la carpeta \CreateRules:<br /><br /> App.ico, AssemblyInfo.cs, Case.xsd, CreateLoanProcessingPolicy.csproj, CreateLoanProcessingPolicy.sln, WriteToBRL.cs|Archivos de proyecto, de solución, de origen y archivos relacionados de Visual C# usados para crear la aplicación que genera, mediante programación, las reglas en el conjunto. Para obtener ejemplos sobre la generación mediante programación de conjuntos de reglas, vea el archivo de origen WriteToBRL.cs.|  
|En la carpeta \myFactRetriever:<br /><br /> AssemblyInfo.cs<br /><br /> FactRetrieverForLoansProcessing.cs<br /><br /> myFactRetriever.csproj<br /><br /> myFactRetriever.sln|Archivos de proyecto, de solución, de origen y archivos relacionados de Visual C# usados para crear un ensamblado que pueda utilizarse para recuperar información de la tabla CustInfo, agregada anteriormente a la base de datos de ejemplo Northwind de SQL Server.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
#### <a name="to-build-and-initialize-the-loans-processing-using-business-rules-sample"></a>Para crear e inicializar el ejemplo Loans Processing Using Business Rules  
  
1.  Asegúrese de que la base de datos Northwind esté instalada en el equipo.  
  
    > [!IMPORTANT]
    >  Para ejecutar este ejemplo, debe disponer de una base de datos con el nombre Northwind. [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] y [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] no se distribuyen con la base de datos Northwind de ejemplo. Para crear la base de datos Northwind, descargue el archivo de instalación de [http://go.microsoft.com/fwlink/?LinkId=196020](http://go.microsoft.com/fwlink/?LinkId=196020)y siga las instrucciones.  
  
2.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*> \Business Rules\Loans Processing using Business Rules  
  
3.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Realiza una limpieza de GAC para eliminar los datos residuales de ejecuciones anteriores de este ejemplo.  
  
    -   Compila e implementa el programa de administrador de almacenes de datos, myFactRetreiever.dll.  
  
    -   Mediante el uso del archivo de secuencia de comandos SQL Create_CustInfo_Table.sql, agrega una tabla llamada CustInfo a la base de datos de ejemplo Northwind de SQL.  
  
    -   Realiza una limpieza del almacén de reglas de SQL compartido para eliminar los residuos de ejecuciones anteriores de este ejemplo.  
  
    -   Crea, publica e implementa la versión más reciente (1.0) del conjunto de reglas de procesamiento de préstamos.  
  
        > [!NOTE]
        >  Puede usar la herramienta Compositor de reglas de negocio que se proporciona con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para examinar las reglas que se han establecido mediante programación.  
  
    -   Crea las carpetas de entrada (In) y de salida (Out) para este ejemplo.  
  
    -   Compila e implementa los proyectos restantes de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] de este ejemplo, incluido el proyecto de BizTalk que contiene la orquestación usada para coordinar el ejemplo.  
  
    -   Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.  
  
        > [!NOTE]
        >  Este ejemplo muestra las siguientes advertencias al crear y enlazar puertos:  
        >   
        >  `Warning: Receive handler not specified for receive location "LoansProcessor_1.0.0.0_LoansProcessor.My_Sample_Service_Incoming_ReceiveLocation"; updating with first receive handler with matching transport type.`  
        >   
        >  `Warning: Host not specified for orchestration "LoansProcessor.My_Sample_Service"; updating with first available host.`  
        >   
        >  Puede omitir estas advertencias de forma segura. (Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).  
  
    -   Habilita la ubicación de recepción e inicia el puerto de envío.  
  
    -   Da de alta e inicia la orquestación.  
  
> [!NOTE]
>  Si su nombre de host de BizTalk no es BizTalkServerApplication, modifique los archivos Setup.bat y LoanProcessorBinding.xml para que reflejen el nombre de host apropiado.  
  
> [!NOTE]
>  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
> [!NOTE]
>  Si opta por abrir y crear los proyectos en este ejemplo sin ejecutar el archivo Setup.bat, primero debe crear un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar los ensamblados resultantes.  
  
> [!NOTE]
>  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-loans-processing-using-business-rules-sample"></a>Para ejecutar el ejemplo Loans Processing Using Business Rules  
  
1.  Pegue una copia del archivo sampleLoan.xml en la **\In** carpeta.  
  
2.  Observe el archivo .xml creado en la carpeta **Out**. Contiene el mensaje de entrada XML con datos agregados a los cuatro elementos siguientes al final de la estructura XML: **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, y **ResidencyStatus**.  
  
 Puede usar la herramienta Compositor de reglas de negocios para cambiar las reglas del conjunto de reglas y volver a implementar esas reglas.  
  
#### <a name="to-use-the-business-rule-composer-tool-to-change-one-or-more-of-the-rules-in-a-rule-set"></a>Para usar la herramienta Compositor de reglas de negocio para cambiar una o varias reglas de un conjunto de reglas  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Compositor de reglas de negocios**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En el **SQL Server** cuadro de diálogo, haga clic en **Aceptar** para conectarse al almacén de reglas.  
  
3.  En **Explorador de directivas**, debajo del nodo **LoanProcessing**, haga clic en el **versión 1.0 – implementada** nodo y, a continuación, haga clic en **copia**.  
  
4.  Haga clic en **LoanProcessing**y, a continuación, haga clic en **pegar**.  
  
5.  Cambie cualquier regla o acción de forma que dará como resultado valores diferentes para la **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, y  **ResidencyStatus** elementos. Asegúrese de que cambia también el valor de la parte de negación (básicamente, el **Else** cláusula) de cualquier regla que desee cambiar.  
  
     La siguiente tabla muestra el conjunto de reglas usado por este ejemplo. A menos que se especifique lo contrario, los hechos provienen del mensaje entrante. La cadena (db) indica una base de datos como el origen de un hecho.  
  
    |Número de regla|Nombre de regla|Description|  
    |-----------------|---------------|-----------------|  
    |1|Regla de estado de entrada|IF **BasicSalary** + **OtherIncome** > 0<br /><br /> A continuación, **IncomeStatus** = **válido**|  
    |2|Regla de estado de confirmación|IF **identificador** == **Id. (db)**<br /><br /> y<br /><br /> IF **CreditCardBalance (db)** > 500<br /><br /> A continuación, **CommitmentsStatus** =<br /><br /> "Compute Commitments"|  
    |3|Regla de estado laboral|IF **EmploymentType &#124; TimeInMonths** > 18<br /><br /> A continuación, **EmploymentStatus** = **válido**|  
    |4|Regla de situación legal|IF **PlaceOfResidence &#124; TimeInMonths** > 18<br /><br /> A continuación, **ResidencyStatus** = **válido**|  
    |!1, !2, !3, !4|Reglas de negación|Las condiciones que son un operador lógico **no** de la condición correspondiente descrita en las reglas 1 – 4. Las acciones resultantes son un cambio en la cadena que se está estableciendo.|  
  
6.  Haga clic en el **versión 1.1 (sin guardar)** nodo y, a continuación, haga clic en **guardar**.  
  
7.  Haga clic en el **versión 1.1** nodo y, a continuación, haga clic en **publicar**.  
  
8.  Haga clic en el **versión 1.1** nodo y, a continuación, haga clic en **implementar**.  
  
9. Espere 60 segundos para que los cambios se propaguen por el almacén de reglas de SQL Server compartido.  
  
10. Pegue una copia del archivo sampleLoan.xml en la carpeta **en**.  
  
11. Observe el archivo .xml creado en la carpeta **Out**. Contiene el mensaje de entrada XML con datos agregados a los cuatro elementos siguientes al final de la estructura XML: **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, y **ResidencyStatus**. Los datos agregados a estos elementos se diferenciarán, o no, de la ejecución anterior, en función de la naturaleza de los cambios realizados en el paso 5 de este procedimiento.  
  
## <a name="comments"></a>Comentarios  
 Si desea ver la información de seguimiento de este ejemplo, debe anular la implementación y volver a implementar el conjunto de reglas correspondiente (procesamiento de préstamos) mediante el uso del Asistente para implementar el Motor de reglas de negocios.  
  
 En este ejemplo se muestra cómo se pueden usar las reglas de negocios para aplicar directivas empresariales en forma de reglas dentro de una orquestación. También se muestra cómo pueden cambiarse las directivas y realizar el cambio en la directiva reflejada de forma dinámica en la orquestación sin tener que volver a compilar o implementar la solución de orquestación.  
  
 Los escenarios de préstamos de entrada de este ejemplo son mensajes XML con la siguiente estructura:  
  
```  
    Name  
    ID  
    Income  
        BasicSalary  
        OtherIncome  
    EmploymentType  
        TimeInMonths  
    PlaceOfResidence  
        TimeInMonths  
    CommitmentsStatus  
    IncomeStatus  
    EmploymentStatus  
    ResidencyStatus  
```  
  
## <a name="see-also"></a>Vea también  
 [Reglas de negocios (carpeta de ejemplos de BizTalk Server)](../core/business-rules-biztalk-server-samples-folder.md)