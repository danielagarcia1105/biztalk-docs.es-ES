---
title: HTTPSSO (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- SSO, examples
- SSO, HTTP adapters
- examples, HTTP adapters
- HTTP adapters, SSO
- examples, SSO
ms.assetid: 322360df-81d2-4a73-9512-bda9382351a2
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41956d9e10cba87e0e1a1f44d49dd8ec8b6039bc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="httpsso-biztalk-server-sample"></a>HTTPSSO (ejemplo de BizTalk Server)
El ejemplo TTPSSO muestra cómo usar la característica Inicio de sesión único empresarial (SSO) con el adaptador de HTTP de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  Este ejemplo no es compatible en sistemas operativos de 64 bits.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo se muestra un escenario completo que usa SSO y los adaptadores de envío y de recepción HTTP de BizTalk para simular cómo SSO permite que un usuario evite tener que proporcionar credenciales adicionales para iniciar sesión en sistemas que no sean de Microsoft Windows después de que Windows los haya autenticado.  
  
 Este ejemplo también usa los módulos de administración y asignación de SSO para crear aplicaciones y asignaciones de SSO afiliadas mediante el uso de DLL clientes de interoperabilidad de SSO.  
  
 El ejemplo muestra el uso de SSO mediante la implementación de los siguientes aspectos de un escenario de un extremo a otro:  
  
-   La interfaz de usuario, representada por un directorio virtual de Microsoft Internet Information Services (IIS) configurado para usar la autenticación integrada de Windows.  
  
-   El sistema de servidor, representado por un directorio virtual de IIS configurado para usar la autenticación básica.  
  
-   La base de datos de servidor, representada por la base de datos de ejemplo de SQL Northwind.  
  
 Este ejemplo da por supuesto que tiene instalado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SSO. Debe tener privilegios de administrador para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], IIS, SSO y COM + en Windows XP Professional. También debe ser miembro de los grupos de Windows Administradores de SSO, Administradores de servidor BizTalk Server y Usuarios de hosts aislados de BizTalk.  
  
 El uso eficaz de este ejemplo presupone que tiene los suficientes conocimientos de SSO y del adaptador de HTTP de BizTalk. Por ejemplo, debe saber lo que es una aplicación afiliada en el contexto de SSO. Para obtener información acerca de estos temas, vea [mediante SSO](../core/using-sso.md). Consulte también [adaptador de HTTP](../core/http-adapter.md).  
  
 Una vez completada la configuración, este ejemplo funciona de la siguiente forma:  
  
1.  Al hacer clic en **finalizar** en la aplicación del asistente que compone la interfaz de usuario para este ejemplo, se inicia una instancia de Internet Explorer y pasa la dirección URL de la DLL de recepción HTTP de BizTalk.  
  
2.  BizTalk Server, con la ayuda de SSO, reenvía de forma eficaz la solicitud de HTTP al archivo EmployeeData.aspx en un directorio virtual de IIS que se ha configurado con la autenticación básica. Este archivo ASPX simula el punto de entrada en un sistema de servidor que no sea de Windows. Puesto que está usando SSO, la solicitud HTTP incluye las credenciales configuradas que simulan una cuenta de inicio de sesión en el sistema de servidor simulado.  
  
3.  El archivo ASPX obtiene acceso a la versión modificada de la base de datos de ejemplo de SQL Northwind para recuperar los datos de empleados correspondientes a las credenciales del sistema de servidor simuladas.  
  
4.  En una respuesta HTTP, el archivo ASPX devuelve los datos de empleados recuperados.  
  
5.  BizTalk Server enruta la respuesta HTTP a Internet Explorer, que muestra los datos de empleados devueltos al usuario.  
  
 Si se salta los pasos de BizTalk Server y SSO, y se desplaza directamente al archivo EmployeeData.aspx, un cuadro de diálogo de Windows se solicitará sus credenciales.  
  
 Para obtener un ejemplo que muestra cómo utilizar la utilidad de línea de comandos ssomanage.exe para configurar SSO, como la creación de aplicaciones afiliadas y asignaciones de usuario, consulte [administrar (ejemplo de BizTalk Server)](../core/manage-biztalk-server-sample.md).  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de ruta de acceso*\>\SSO\HTTPSSO\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs, SsoSample.csproj|Archivos de proyectos y archivos relacionados para este ejemplo de SSO de HTTP.|  
|SsoSample.cs|Archivo de origen de nivel superior Microsoft Visual C# para la aplicación gráfica de SSO de HTTP, que constituye gran parte de este ejemplo. Este archivo contiene el código de configuración de SSO, en una clase denominada **SsoConfigurator** que en última instancia es el punto de este ejemplo.|  
|En la carpeta \Scripts:<br /><br /> EmployeeData.aspx|Se usa para obtener acceso a la base de datos de servidor y consultarla (en este caso, se trata de la base de datos Northwind de SQL) cuando un empleado inicia una solicitud para ver datos personales, ya sea de forma directa o mediante el uso de SSO.|  
|En la carpeta \Scripts:<br /><br /> ValidateUser.aspx|Prueba sencilla para validar un usuario e informar si el usuario está validado, ya sea de forma directa o mediante el uso de SSO.|  
|En la carpeta \UI:<br /><br /> AddApplication.cs, AddApplication.resx, AddMapping.cs, AddMapping.resx, App.ico, BtsPage.cs, BtsPage.resx, ExecutePage.cs, ExecutePage.resx, FinishPage.cs, FinishPage.resx, IisPage.cs, IisPage.resx, InfoPage.cs, InfoPage.resx, PageBase.cs, PageBase.resx, SsoPage.cs, SsoPage.resx, SsoSampleWizard.cs, SsoSampleWizard.resx, WelcomePage.cs, WelcomePage.resx, WorkPage.cs, WorkPage.resx|Archivos de origen auxiliares de Visual C#, y sus archivos asociados de recurso con formato XML, para la aplicación gráfica de SSO de HTTP, que constituye gran parte de este ejemplo.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
#### <a name="to-build-and-initialize-the-httpsso-sample"></a>Para crear e inicializar el ejemplo HTTPSSO  
  
1.  Cree una cuenta local de Windows que pueda usar Microsoft Internet Information Services (IIS) para la autenticación básica. SSO asigna la cuenta de dominio de Windows para esta cuenta local de Windows. Por ejemplo, use sus apellidos para crear una cuenta local de Windows.  
  
    > [!NOTE]
    >  Si se está ejecutando en un controlador de dominio, puede crear una cuenta de dominio y asignar su cuenta de dominio con la que ha iniciado sesión a esta cuenta.  
  
2.  Mediante el Administrador corporativo de Microsoft SQL Server, abra el **empleados** tabla en la base de datos de ejemplo Northwind y, a continuación, agregue una fila que corresponda a la cuenta de Windows local que acaba de crear, incluidos los datos de ejemplo para los distintos columnas. El valor que agregue a la columna Apellido en la tabla Empleados debe ser el mismo que el del nombre de usuario de la cuenta local de Windows agregada en el paso 1.  
  
3.  Asegúrese de que la cuenta ASP.NET (ASPNET) tiene privilegios de lectura para la base de datos Northwind.  
  
4.  Abra el archivo de proyecto SsoSample.csproj con Visual Studio.  
  
5.  En el menú **Compilar** , haga clic en **Compilar solución**.  
  
    > [!NOTE]
    >  Puede que se le solicite que guarde un archivo de solución antes de que se pueda proceder a la creación.  
  
     Si no encuentra las siguientes referencias de ensamblado de BizTalk del proyecto, elimínelas, vuelva a agregarlas desde las ubicaciones indicadas y créelas de nuevo:  
  
    -   **Microsoft.BizTalk.ExplorerOM**. De forma predeterminada, el archivo Microsoft.BizTalk.ExplorerOM.dll se encuentra en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools\\.  
  
    -   **Microsoft.BizTalk.SSOClient.Interop**. De forma predeterminada, el archivo Microsoft.BizTalk.Interop.SSOClient.dll se encuentra en la carpeta \< *ProgramFiles*\>\Common Files\Enterprise Single Sign-On\\.  
  
     Con esto, se produce el archivo ejecutable SsoSample.exe en la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\SSO\HTTPSSO\bin\Debug\  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
> [!NOTE]
>  Si ejecuta este ejemplo en IIS 6.0 en el modo aislado del proceso de trabajo, los grupos de aplicaciones se crean para ambos directorios virtuales. Debe configurar manualmente la identidad de estos dos grupos de aplicaciones en su cuenta de Windows (puede configurar la identidad en el Administrador de servicios de Internet Information Server).  
  
#### <a name="to-run-the-httpsso-sample"></a>Para ejecutar el ejemplo de HTTPSSO  
  
1.  Ejecute el archivo ejecutable SsoSample.exe, que se encuentra en la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\SSO\HTTPSSO\bin\Debug\  
  
     La aplicación del asistente de este ejemplo se abre.  
  
2.  En la página de bienvenida, acepte la configuración predeterminada para configurar IIS, SSO y BizTalk y, a continuación, haga clic en **siguiente**.  
  
3.  En la página de configuración de IIS, acepte la configuración predeterminada para los dos directorios virtuales de IIS que desea crear y, a continuación, haga clic en **siguiente**.  
  
4.  En la página de configuración de SSO, acepte la configuración predeterminada para la aplicación afiliada, que se puede obtener acceso mediante la **Agregar aplicación** botón.  
  
5.  En la página de configuración de SSO, acepte la mayor parte de la configuración predeterminada para las asignaciones de usuario, puede obtener acceso mediante la **Agregar asignación** botón. Proporciona valores para las siguientes dos configuraciones basándose en la cuenta local de Windows agregada durante la creación e inicialización de este ejemplo.  
  
    |Configuración|Valor|  
    |-------------|-----------|  
    |Nombre de usuario externo|Establecido como el nombre de la cuenta de usuario de Windows local agregado.|  
    |Contraseña de usuario externa|Establecida como la contraseña de la cuenta de usuario de Windows local agregada.|  
  
6.  En la página de configuración de SSO, haga clic en **siguiente**.  
  
7.  En la página de configuración de BizTalk, acepte la configuración predeterminada para el envío y puertos de recepción y así sucesivamente y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Puede cambiar la configuración del puerto de envío predeterminada de **EmployeeData.aspx** a **ValidateUser.aspx** si desea ver la validación de usuario simple en lugar de datos de ejemplo que se extraigan de la tabla de empleados de la Base de datos Northwinds de SQL. Al realizar este cambio modifica la naturaleza del resultado que aparece en el explorador después de hacer clic **finalizar** en el paso 9.  
  
8.  Revise los mensajes de estado correspondientes a la configuración de IIS, SSO y BizTalk que se está realizando. Puede encontrar el código que se ejecuta durante esta fase en la **IisConfigurator**, **SsoConfigurator**, y **BtsConfigurator** clases definidas en el archivo SsoSample.cs. Una vez finalizada la configuración, haga clic en **siguiente**.  
  
9. En la página final de la aplicación del asistente, acepte la configuración predeterminada de **Iniciar explorador en** (la casilla está activada y un cuadro de texto con la dirección URL http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?<message/>), y, a continuación, haga clic en **finalizar**.  
  
     Se abrirá una instancia de Internet Explorer, y pronto aparecerán los datos del empleado de ejemplo que ha agregado a la tabla Empelado de la base de datos Northwinds de SQL.  
  
 Para realizar una comparación, puede pasar por alto BizTalk y SSO y dirigirse directamente a alguno de los archivos ASPX:  
  
-   http://localhost/SsoSampleServerApplication/ValidateUser.aspx  
  
-   http://localhost/SsoSampleServerApplication/EmployeeData.aspx  
  
 En ambos casos, dado que se ha saltado los pasos de BizTalk y SSO, IIS le solicitará la información de su autenticación (use la información de la cuenta local de Windows creada anteriormente).  
  
## <a name="comments"></a>Comentarios  
 La aplicación del asistente de SsoSample.exe configura dos directorios virtuales de IIS:  
  
-   El primer directorio virtual está configurado con la autenticación integrada de Windows, y corresponde a la extensión ISAPI de recepción HTTP de BizTalk. Debe estar asociado al archivo BTSHTTPReceive.dll, que se encuentra en la siguiente carpeta:  
  
     \<*La ruta de instalación*\>\HttpReceive  
  
-   El segundo directorio virtual está configurado con la autenticación básica, y simula un sistema de servidor que acepta una contraseña y un Id. de usuario para que el usuario se autentique. Debe estar asociado a uno de los archivos ASPX: ValidateUser.aspx o EmployeeData.aspx que se encuentran en la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\SSO\HTTPSSO\Scripts  
  
 Puede usar la aplicación del asistente de SsoSample.exe para configurar una o varias aplicaciones afiliadas. Para cada una de estas aplicaciones afiliadas, puede crear una o varias asignaciones de usuario. Cada una de estas asignaciones de usuario asigna una cuenta de usuario de Windows a una cuenta que se use para obtener acceso a un sistema de servidor específico. En este ejemplo, se trata de una cuenta local de Windows que se usa para la autenticación con el segundo directorio virtual de IIS, que está simulando un sistema de servidor original.  
  
 Para volver a ejecutar este ejemplo, puede realizar lo siguiente:  
  
-   En Internet Explorer, desplácese directamente a la siguiente URL:  
  
     http://localhost/SsoSampleBizTalkHttpReceive/BTSHTTPReceive.dll?<message/>  
  
-   Ejecute de nuevo la aplicación del asistente, pero borre todas las casillas de verificación de configuración de la primera página.  
  
-   Vuelva a ejecutar la aplicación del asistente, deje las casillas de verificación de configuración seleccionadas en la primera página, pero configure cuidadosamente y de forma adecuada los elementos adicionales de BizTalk, las aplicaciones afiliadas, etc., para que no se produzcan errores de configuración.  
  
 Para borrar desde este ejemplo, use el siguiente procedimiento.  
  
#### <a name="to-clean-up-from-this-sample"></a>Para limpiar desde este ejemplo  
  
1.  Según corresponda, invierta la configuración manual realizada, por ejemplo, quitando la cuenta local de Windows.  
  
2.  Quite las aplicaciones de IIS que correspondan a los directorios virtuales y, a continuación, elimine los directorios virtuales de IIS creados por este ejemplo.  
  
3.  Con la consola de administración de BizTalk, puede dar de baja y eliminar el puerto de envío asociado a este ejemplo. Después, elimine el puerto de recepción (y su ubicación de recepción) asociado a este ejemplo.  
  
4.  Use la aplicación Ssomanage (ubicada en \Program Files\Common Files\Enterprise Single Sign-On\\) para eliminar la aplicación de SSO para este ejemplo:  
  
    ```  
    Ssomanage –deleteapp SsoSampleApplication  
    ```  
  
## <a name="see-also"></a>Vea también  
 [SSO (carpeta de ejemplos de BizTalk Server)](../core/sso-biztalk-server-samples-folder.md)