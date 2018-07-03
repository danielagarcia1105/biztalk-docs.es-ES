---
title: Medical Claims Processing and Testing Policies (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: c0bdf7b7-3e55-4560-a5a8-00c5b661d14d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e67b9a631764ed83659b05aa11f4c1570484f74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994869"
---
# <a name="medical-claims-processing-and-testing-policies-biztalk-server-sample"></a>Medical Claims Processing and Testing Policies (ejemplo de BizTalk Server)
El ejemplo Medical Claims Processing and Testing Policies muestra cómo crear un conjunto de reglas compuesto por varias reglas que examinen hechos derivados de una tabla de la base de datos y del documento entrante, y que usan objetos basados en .NET para registrar los resultados del procesamiento de reclamaciones.  
  
 Este ejemplo muestra la ejecución integral del escenario de procesamiento de reclamaciones mediante una aplicación sencilla basada en .NET que usa el Motor de reglas de negocios para ejecutar un conjunto de reglas de reclamaciones médicas en las reclamaciones entrantes y determinar el estado (STATUS) de la reclamación y la razón (REASON) de dicho estado.  
  
> [!NOTE]
>  Este ejemplo también muestra como realizar el seguimiento de la ejecución del Motor de reglas de negocios mediante un archivo de seguimiento de depuraciones.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo aplica la secuencia de reglas siguiente a las reclamaciones enviadas:  
  
1.  Rechaza la reclamación si el importe total reclamado supera el máximo permitido por la póliza.  
  
2.  Rechaza la reclamación si el cliente ha estado en el hospital más noches que el máximo permitido por la póliza.  
  
3.  Rechaza la reclamación si la fecha que figura en ella está en el futuro.  
  
4.  Rechaza la reclamación si la póliza no es válida.  
  
5.  Si la póliza ha vencido, envía una indicación al departamento de ventas con el Id. de la póliza y el nombre del cliente.  
  
6.  En caso contrario, aprueba la reclamación.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de la ruta de acceso*\>\Business Rules\Medical Claims Processing and Testing Policies\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Descripción|  
|---------------|-----------------|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC). Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|Create_PolicyValidity_Table.sql|Secuencia de comandos SQL que agrega una tabla nueva con el nombre PolicyValidity a la base de datos de ejemplo Northwind.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
|En la carpeta \Claims:<br /><br /> AssemblyInfo.cs, Claims.csproj, Claims.sln, Claims.cs|Proyecto, solución, origen y archivos relacionados para la parte de este ejemplo que registra el resultado de las notificaciones de procesamiento, denominan el **, a continuación,** parte de una regla.|  
|En la carpeta \FactRetrieverForClaimsProcessing:<br /><br /> AssemblyInfo.cs, FactRetrieverForClaimsProcessing.cs, FactRetrieverForClaimsProcessing.csproj, FactRetrieverForClaimsProcessing.sln|Archivos del proyecto, la solución, de origen y relacionados correspondientes a la parte de este ejemplo que proporciona el administrador de almacenes de datos a largo plazo que recupera información de la tabla PolicyValidity creada por este ejemplo.|  
|En la carpeta \RulesForMedicalClaims:<br /><br /> App.ico, AssemblyInfo.cs, RulesForMedicalClaims.cs, RulesForMedicalClaims.csproj, RulesForMedicalClaims.sln|Proyecto, solución, origen y archivos relacionados para la parte de este ejemplo que constituye el ejecutable principal para este ejemplo (RulesForMedicalClaims.exe) y que, mediante programación define y almacena el conjunto de reglas, construye datos de ejemplo y, a continuación, se ejecuta el conjunto de reglas mediante un **PolicyTester** objeto.|  
|En la carpeta \RulesForMedicalClaims:<br /><br /> MedicalClaims.xsd|Archivo de esquema que define la estructura de las reclamaciones médicas de ejemplo enviadas a este ejemplo.|  
|En la carpeta \RulesForMedicalClaims:<br /><br /> sampleClaim.xml|Archivo de entrada de ejemplo que se ajusta al esquema definido en el archivo MedicalClaims.xsd.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
#### <a name="to-build-and-initialize-the-medical-claims-processing-and-testing-policies-sample"></a>Para crear e inicializar el ejemplo Medical Claims Processing and Testing Policies  
  
1. Asegúrese de que la base de datos Northwind esté instalada en el equipo.  
  
   > [!IMPORTANT]
   >  Para ejecutar este ejemplo, debe tener la base de datos de ejemplo Northwind de SQL Server. [Descargar](https://www.microsoft.com/download/details.aspx?id=23654)e instalar. 
  
2. En una ventana de comandos, desplácese a la siguiente carpeta:  
  
    \<*Ejemplos de la ruta de acceso*\>\Business Rules\Medical Claims Processing and Testing Policies\  
  
3. Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
   - Compila e implementa los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] correspondientes a este ejemplo, incluidos Claims.dll, FactRetrieverForClaimsProcessing.dll y RulesForMedicalClaims.dll.  
  
   > [!NOTE]
   >  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
   > 
   > [!NOTE]
   >  Si opta por abrir y crear los proyectos de este ejemplo sin ejecutar el archivo Setup.bat, debe crear primero un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar los ensamblados resultantes.  
  
   - Ejecuta la secuencia de comandos SQL suministrada Create_PolicyValidity_Table.sql mediante el Analizador de consultas SQL. La secuencia de comandos crea la tabla, PolicyValidity, con dos filas de ejemplo en la base de datos de ejemplo Northwind. Esta tabla tiene dos columnas: ID y PolicyStatus.  
  
   - Crea y enlaza los puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
   - Habilita la ubicación de recepción e inicia el puerto de envío.  
  
   - Da de alta e inicia la orquestación.  
  
   > [!NOTE]
   >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-medical-claims-processing-and-testing-policies-sample"></a>Para ejecutar el ejemplo Medical Claims Processing and Testing Policies  
  
1. En una ventana de comandos, desplácese a la siguiente carpeta:  
  
    \<*Ejemplos de la ruta de acceso*\>\Business Rules\Medical Claims Processing and Testing Policies\RulesForMedicalClaims\bin\Debug\  
  
2. Ejecute el archivo RulesForMedicalClaims.exe en la línea de comandos.  
  
   > [!NOTE]
   >  Puede cambiar los valores de los elementos individuales en el archivo de reclamaciones de ejemplo (sampleClaim.xml) y ejecutar el ejemplo varias veces. La lista que figura a continuación muestra los resultados previstos para los distintos valores de estos elementos.  
  
   Los escenarios de resultados basados en las diversas combinaciones de valores en el archivo de reclamaciones de ejemplo enviado son:  
  
-   En el caso de una reclamación cuyo importe supere los 1000 dólares, se obtiene el resultado siguiente:  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of claim has exceeded Policy limit  
    ```  
  
-   En el caso de una reclamación cuyo número de noches sea superior a 10, se obtiene el resultado siguiente:  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of Nights has exceeded Policy limit  
    ```  
  
-   En el caso de una reclamación cuya fecha no sea válida (fecha > fecha actual), se obtiene el resultado siguiente:  
  
    ```  
    Status:  REJECTED!  
    Reason:  Cannot submit claims for future dates!  
    ```  
  
-   Para una notificación con un identificador de directiva que no es válido (por ejemplo, cambiando el **ID** elemento tenga un valor de 2) debido a la expiración de la directiva, se obtiene el resultado siguiente:  
  
    ```  
    Sending to Renewal Department for Customer Smir with Policy # 2  
    Status:  REJECTED!  
    Reason:  Policy ID is invalid  
    ```  
  
-   En el caso de una reclamación válida, se obtiene el resultado siguiente:  
  
    ```  
    Status:  Claim Accepted!  
    Reason:  
    ```  
  
    > [!NOTE]
    >  Cada vez que ejecute este ejemplo, se creará un archivo de texto (outputtrace.txt) en la carpeta ...\RulesForMedicalClaims\bin\Debug. Contiene un seguimiento de depuración de la ejecución de la regla y se crea tras cada ciclo de ejecución en la carpeta \RulesForMedicalClaims\bin\Debug. Puede examinar este archivo para ver el seguimiento de resultados de la ejecución de la regla.  
  
## <a name="comments"></a>Comentarios  
 Los orígenes de los datos empleados en la evaluación del conjunto de reglas son:  
  
- Un administrador de almacenes a largo plazo, una. Aplicación basada en red que implementa el **IFactReriever** interfaz, se crea en la carpeta FactRetrieverForClaimsProcessing. La directiva de procesamiento de reclamaciones médicas lo emplea para recuperar datos (con forma de conjunto de datos) de la base de datos PolicyValidity y para la evaluación de las condiciones de las reglas.  
  
- La notificación es en forma de un documento XML que contiene la siguiente información almacenada en elementos hermanos: nombre, identificador, cantidad, noches y fecha.  
  
- UN OBJETO. Biblioteca de clases basado en la red (notificaciones), con un **ClaimResults** clase se utiliza para registrar el estado y el motivo de la reclamación mediante propiedades y para enviar una indicación (si la directiva no es válida) invocando el **SendLeads** método con ID y name como parámetros.  
  
  Según estos orígenes de los datos, se pueden describir de manera informal las reglas definidas para este escenario del siguiente modo:  
  
1. Comprobar si la reclamación entrante es válida. La reclamación no es válida si el importe supera el límite permitido para una reclamación, si la póliza ha vencido (verificado mediante la comprobación de la tabla de la base de datos), si el número de noches supera el límite máximo permitido y si se ha realizado la reclamación para una fecha en el futuro. Si se ha determinado que la reclamación no es válida, establecer los valores de STATUS y REASON de la reclamación de forma adecuada.  
  
2. Si el Id. de la póliza de la reclamación entrante ha vencido, enviar una indicación (con el Id. de la póliza y el nombre del cliente) al departamento de renovación de pólizas.  
  
3. Si la reclamación es válida, establecer los valores de STATUS y REASON de la reclamación de forma adecuada.  
  
   Una representación más formal de las reglas y sus enlaces de términos es la siguiente:  
  
-   **Regla 1. Comprobación de cantidad**  
  
    ```  
    IF Amount in the XML document is > 1000  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"\  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **Regla 2. Noches empleadas en el hospital**  
  
    ```  
    IF number of nights in the XML document is > 10  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **Regla 3. Fecha de validez**  
  
    ```  
    IF date on the incoming XML claim is > Today  
      AND   
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Cannot submit claims in the future!"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **Regla 4. Validez de la directiva**  
  
    ```  
    IF Policy is invalid for the ID in the XML claim (check database)  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Policy Invalid"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **Regla 5. Ventas potenciales**  
  
    ```  
    IF Claim.ClaimResults.Reason = "Policy invalid"  
  
    THEN send a lead to the policy department by invoking the function Claim.ClaimResults.SendLead with customer ID and Name from the incoming XML document.  
  
    ```  
  
-   **Regla 6. Reclamación aceptada**  
  
    ```  
    IF Claim.ClaimResults.Status = null  
  
    THEN Set the claim status to be valid  
         &&  
         Send the lead to the sales department  
  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Reglas de negocio (carpeta de ejemplos de BizTalk Server)](../core/business-rules-biztalk-server-samples-folder.md)