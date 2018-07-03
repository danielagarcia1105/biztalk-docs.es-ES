---
title: Registrar los pasos de instalación de módulo de adaptador de BizTalk 2016 | Microsoft Docs
description: Pasos para completar después de instalar BAP 2016, incluido agregan adaptador de administración de BizTalk, actualización de Oracle y enlaces del adaptador de registro.
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8946bfe-92bb-470d-bec4-9bc3a07ce0d2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43a454e1e6f1dc65d8a2e2c5493aacf9375374b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997381"
---
# <a name="post-installation-steps-for-biztalk-adapter-pack-2016"></a>Pasos posteriores a la instalación de módulo de adaptador de BizTalk 2016
Después de instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], hay algunos pasos posteriores a la instalación. En este tema se enumera estos pasos.   

## <a name="add-the-adapter-to-biztalk-administration"></a>Agregar el adaptador para la administración de BizTalk

1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. Expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, seleccione **adaptadores**.  

3. Haga clic en **adaptadores**, seleccione **New**y seleccione **adaptador**.  

    ![Agregar un adaptador](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  

4. En el **propiedades del adaptador**, seleccione un adaptador en la lista desplegable, como **SAP de WCF**y, a continuación, escriba un nombre, como **SAP de WCF**.  

    ![Agregar adaptador SAP a BizTalk](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")  

5. Seleccione **Aceptar**.  

## <a name="use-a-newer-oracledataaccessdll-version"></a>Usar una versión más reciente de Oracle.DataAccess.dll  

Al configurar un puerto para utilizar el adaptador de WCF-OracleDB o usar Visual Studio para consumir un adaptador generado, se muestra un mensaje que el adaptador necesita Oracle.DataAccess.dll versión 2.111.7.0. Para resolver este mensaje, instale una versión compatible de Oracle.DataAccess.dll (consulte [admite la lista de versiones](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)) y, a continuación, actualice el `bindingRedirect` elemento en el archivo de configuración de OracleDB mediante los siguientes pasos:  

1.  En el servidor BizTalk Server, vaya a las siguientes carpetas:  

     *unidad*: \Program Files\Microsoft BizTalk Adapter Pack (x64) \bin  

     *unidad*: \Program archivos (x86) \Microsoft BizTalk Adapter Pack\bin  

2.  Abra el archivo Microsoft.Adapters.OracleDB.config.  

3.  Busque la sección siguiente y, a continuación, copiar y pegar lo siguiente:  

    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  

    ```  

    > [!NOTE]
    >  En este ejemplo, establecemos *newVersion* a 2.112.1.00. Establezca este valor en la versión que tenga instalada.  

> [!IMPORTANT]
> - Si hay varios servidores de BizTalk en este grupo, debe realizar este cambio en todos los servidores de BizTalk en el grupo.  
> - El *newVersion* valor debe actualizarse en función de la versión del archivo Oracle.DataAccess.dll instalado en el equipo.  Oracle.DataAccess.dll se incluye con el cliente de Oracle se instala desde Oracle.  Solo se debe instalar una versión de cliente de Oracle que está [compatibles con BizTalk Adapter Pack](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx).  

## <a name="create-sql-server-database-objects-sap-adapter-only"></a>Crear objetos de base de datos de SQL Server (solo para el adaptador SAP)  
 Para invocar trfc en un sistema SAP, ejecute el *SapAdapter-DbScript-Install.sql* secuencia de comandos SQL. Este script se instala con el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación y crea objetos de base de datos en SQL Server. El script se instala normalmente en *\<unidad de instalación\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*. Puede ejecutar este script en cualquier base de datos de SQL Server, siempre y cuando escriba ese nombre de base de datos mientras se usa el adaptador para invocar trfc.

## <a name="register-the-adapter-bindings"></a>Registrar los enlaces del adaptador
Durante la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación, el Asistente para la instalación puede producir un error al registrar los enlaces del adaptador o el proveedor de datos de .NET Framework para mySAP Business Suite. Y el programa de instalación continúa con la instalación del adaptador. Esto puede deberse a la instalación de Windows Communication Foundation (WCF), el [!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)] instalación o el archivo machine.config estén dañados.  

> [!IMPORTANT]
> Complete los pasos siguientes *sólo* si se produce un error en el Asistente para instalación registrar los enlaces del adaptador, o proveedores de datos de .NET Framework en el archivo machine.config.  

1. Vaya al archivo machine.config en el equipo. Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config  *\<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG*.  

2. Abra el archivo con un editor de texto.  

3. Registrar los enlaces del adaptador:  

   1. Busque el `system.serviceModel` elemento y agregue lo siguiente en él:  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. Busque el `bindingElementExtensions` elemento bajo system.serviceModel\extensions.  

   3. Busque el enlace del adaptador que faltan. Agregue las siguientes secciones en el `bindingElementExtensions` nodo, dependiendo del enlace del adaptador que faltan. Debe registrar todos los enlaces si se produce un error en el Asistente para instalación registrar cualquiera.  

       Para el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], agregue:  

      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       Para el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], agregue:  

      ```  
      <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       Para el [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], agregue:  

      ```  
      <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       Para el [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], agregue:  

      ```  
      <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       Para el [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], agregue:  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. Busque el `bindingExtensions` elemento bajo system.serviceModel\extensions.  

   5. Busque el enlace del adaptador que faltan. Agregue las siguientes secciones en el `bindingExtensions` nodo, dependiendo del enlace del adaptador que faltan. Debe registrar todos los enlaces si se produce un error en el Asistente para instalación registrar cualquiera.  

       Para [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], agregue:  

      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       Para [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], agregue:  

      ```  
      <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       Para [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], agregue:  

      ```  
      <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       Para [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], agregue:  

      ```  
      <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       Para [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], agregue:  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  Para obtener el valor de clave público, consulte **determinar la clave pública y la versión** (en este tema).  

4. Registre los proveedores de datos de .NET Framework:  

   1. Busque el `DbProviderFactories` elemento bajo el nodo system.data.  

   2. Busque los proveedores de datos de .NET Framework que falta. Agregue las siguientes secciones en el `DbProviderFactories` nodo, en función del proveedor que falta. Debe registrar todos los proveedores de si se produce un error en el Asistente para instalación registrar cualquiera.  

       Para el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], agregue:  

      ```  
      <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
          description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       Para el [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], agregue:  

      ```  
      <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
          description=".NET Framework Data Provider for Siebel eBusiness Applications"  
          type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. Guarde y cierre el archivo machine.config.  

## <a name="determine-the-public-key-and-version"></a>Determinar la clave pública y la versión  
 Complete los pasos siguientes para determinar la clave pública y la versión para un adaptador o el proveedor de datos de .NET Framework.  

1. Vaya al directorio de Windows, normalmente *C:\WINDOWS\assembly*.  

2. Haga clic en el archivo DLL para el que desea que la clave pública y, a continuación, seleccione **propiedades**. En la tabla siguiente se muestra el nombre de los archivos DLL para cada adaptador y el proveedor:  


   |                         Proveedor de datos de adaptador y .NET Framework                         |       Nombre del archivo DLL        |
   |--------------------------------------------------------------------------------------|------------------------------|
   |           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |    Microsoft.Adapters.SAP    |
   |        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |  Microsoft.Adapters.Siebel   |
   |        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        | Microsoft.Adapters.OracleDB  |
   | [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] | Microsoft.Adapters.OracleEBS |
   |            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |  Microsoft.Adapters.Sql.dll  |
   |        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |   Microsoft.Data.SAPClient   |
   |     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | Microsoft.Data.SiebelClient  |


3. En el **General** ficha, el **Token de clave pública** valor es la clave pública para el archivo DLL. El **versión** valor es el número de versión para el archivo DLL.  

4. Copie la clave pública y, a continuación, seleccione **cancelar**.  

## <a name="install-the-custom-rfcs"></a>Instalar la RFC personalizadas  
Solo es necesario *si* que desea usar el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]. Consulte [instalar personalizado RFC](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md) en el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] documentación. 

> [!IMPORTANT]
>  Si está utilizando una versión anterior de la RFC personalizadas que se valió la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], que debe actualizar a la RFC proporcionada con esta versión. Hacer esto mediante la eliminación de los documentos RFC anteriores y, a continuación, instalar las RFC incluida con esta versión.  

## <a name="install-the-enterprise-applications"></a>Instalar las aplicaciones empresariales  
Para que los pasos y orientación para instalar los sistemas de LOB de la empresa diferente, se recomienda que usar las guías de instalación proporcionadas por el sistema de la empresa. También consulte su documentación del adaptador para cambios de configuración específica, si existe.   

## <a name="installation-and-post-installation-checklist"></a>Lista de comprobación de instalación y posteriores a la instalación  

- Asegúrese de que ha instalado todo el [requisitos previos de software](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) con la opción de instalación correcta.

- Asegúrese de que tiene la versión admitida de las aplicaciones de LOB enterprise instalado en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Consulte [sistemas admitidos línea de negocio (LOB)](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx).  

- Para instalar sólo el adaptador para la empresa del sistema LOB que desea conectarse, asegúrese de que ha instalado el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] utilizando el **personalizado** opción de instalación. Asegúrese de que no ha usado el **completar** opción de instalación. Consulte [instalar BizTalk Adapter Pack](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md).  

- Si desea realizar llamadas de tRFC al sistema SAP con el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], asegúrese de crear las tablas necesarias en una base de datos de SQL Server. Consulte **objetos de base de datos de creación de SQL Server** (en este tema).

- Mientras se está ejecutando el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Asistente para la instalación, puede aparecer un mensaje de error que indica que el programa de instalación no se pudo registrar los enlaces. Si es así, registrarlos manualmente. Consulte **registrar los enlaces del adaptador** (en este tema).  

- Si decide instalar la [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)] como parte de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación, asegúrese de instalar la RFC personalizadas en el sistema SAP. Consulte [instalar RFC personalizadas](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).

## <a name="more-good-info"></a>Obtener más información buena
[Cambiar o quitar BizTalk Adapter Pack](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)  
[BizTalk Adapter Pack preguntas más frecuentes](../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)