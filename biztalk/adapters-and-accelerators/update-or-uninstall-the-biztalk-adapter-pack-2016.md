---
title: "Actualizar o desinstalar el módulo de adaptador de BizTalk 2016 | Documentos de Microsoft"
description: "Usar el Asistente para la instalación o msiexec para cambiar o desinstalar 2016 BAP incluidos con BizTalk Server; incluidos los quite los enlaces y quite las RFC personalizadas"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3d6c001-1005-4d7b-a143-eaa37b48f898
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb0dd0b9d778f878df9a06efdfc0f41754403690
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="update-or-uninstall-the-biztalk-adapter-pack-2016"></a>Actualizar o desinstalar el módulo de adaptador de BizTalk 2016
Cómo cambiar o desinstalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].

<a name="BKMK_Modify_Adap"></a>
## <a name="change-or-update-the-installation"></a>Cambiar o actualizar la instalación  
Antes de ejecutar el Asistente para la instalación para modificar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación, asegúrese de que el [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] está instalado. 
  
 Puede modificar la instalación en modo interactivo (el Asistente para la instalación), o en modo silencioso (la línea de comandos).
  
### <a name="use-the-setup-wizard"></a>Use el Asistente para la instalación  
  
1.  Inicie sesión con una cuenta que sea miembro del grupo Administradores de BizTalk Server.  
  
2.  En **programas y características**, seleccione **desinstalar un programa**.  
  
3.  Haga clic en **Microsoft BizTalk Adapter Pack**y, a continuación, seleccione **cambio**.  
  
4.  En la pantalla de bienvenida, seleccione **siguiente**.  
  
5.  En **cambiar, reparar o quitar instalación**:  
  
    -   Para seleccionar los componentes que desea instalar, seleccione **cambio** y vaya al paso 6.  
  
    -   Para reparar los errores en la instalación más reciente, seleccione **reparar** y vaya al paso 7.  
  
    -   Para quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en el equipo, seleccione **quitar** y, a continuación, vaya al paso 10.  
  
6.  Si decide modificar la instalación:  
  
    -   Expanda el **Microsoft BizTalk Adapter Pack** nodo optar por instalar los adaptadores de base, los proveedores de datos de .NET Framework o ambos.  
  
    -   Expanda el **Base adaptadores** nodo optar por instalar todos los adaptadores o adaptadores específicos.  
  
    -   Expanda el **ADO proveedores** nodo optar por instalar todos los proveedores o proveedores específicos.  
  
    -   Seleccione **Siguiente**.  
  
    -   Seleccione **cambio**y, a continuación, seleccione **finalizar**.  
  
7.  Si decide reparar la instalación, en la **preparado para reparar Microsoft BizTalk Adapter Pack** cuadro de diálogo, seleccione **reparar**. Inicia el Asistente para reparar la instalación.  
  
8.  Si es necesario, cambie las preferencias en relación con la aceptación de CEIP y, a continuación, seleccione **Aceptar**. 
  
9. Seleccione **Finalizar**.  
  
10. Si decide quitar los adaptadores, en el **listo para quitar Microsoft BizTalk Adapter Pack** cuadro de diálogo, seleccione **quitar**y, a continuación, seleccione **finalizar**.  
  
### <a name="use-msiexec-in-silent-mode"></a>Usar msiexec en modo silencioso  
  
1.  Abra un símbolo del sistema y vaya al directorio raíz de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalador.  
  
2.  Ejecute un comando similar al siguiente:  
  
    > [!NOTE]
    >  Para modificar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación en modo silencioso en una plataforma basada en x64, en los siguientes comandos, reemplace `AdaptersSetup.msi` con `AdaptersSetup64.msi`.  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     Este comando quita el [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]e instala el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].  
  
     Mediante el uso de valores diferentes para la `REMOVE` y `ADDLOCAL` propiedades, puede agregar o quitar componentes específicos. Hacer referencia a la tabla de **instalar en modo silencioso** en [instalar BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) para obtener información acerca de los valores que puede usar para estas propiedades.  
  
     También puede hacer una reparación silenciosa mediante la opción/f como parte del comando msiexec. Por ejemplo:  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     Puede utilizar diversas combinaciones diferentes con la opción/f. Para obtener más información sobre el tipo de comando msiexec `msiexec` en la línea de comandos y presione `ENTER`. O vaya a [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).  
  
    > [!IMPORTANT]
    >  Al modificar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación en modo silencioso, no se puede cambiar sus preferencias para participar o excluir el CEIP. Las preferencias que seleccionó durante la instalación se conserva, incluso si se establece explícitamente el CEIP_OPTIN en true o false.  

## <a name="uninstall-or-remove-the-biztalk-adapter-pack"></a>Desinstalar o eliminar el módulo de adaptador de BizTalk  
  
> [!IMPORTANT]
>  Si ha creado las tablas en la base de datos de SQL Server para que funcione con la característica de tRFC de la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], debe quitarlos manualmente antes de desinstalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] de instalación copia un `SapAdapter-DbScript-Uninstall.sql` archivos normalmente en  *\<unidad de instalación\>: \Program [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]* . Ejecute este archivo para quitar las tablas que creó.  
  
Complete los pasos siguientes para quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] desde su equipo. Asegúrese de que tiene el [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] instalado antes de ejecutar el Asistente para la instalación.  
  
 Puede quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en modo interactivo (Asistente para la instalación), o en modo silencioso (línea de comandos).
  
### <a name="uninstall-using-the-setup-wizard"></a>Desinstalar mediante el Asistente para la instalación  
  
1.  En **programas y características**, seleccione **desinstalar un programa**.  
  
2.  Haga clic en **Microsoft BizTalk Adapter Pack**y, a continuación, seleccione **desinstalar**.  
  
### <a name="uninstall-in-silent-mode"></a>Desinstalar en modo silencioso  
  
1.  Abra un símbolo del sistema y vaya al directorio raíz de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalador.  
  
2.  Ejecute el siguiente comando:  
  
    > [!NOTE]
    >  Para quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en modo silencioso en una plataforma basada en x64, en los siguientes comandos, reemplace `AdaptersSetup.msi` con `AdaptersSetup64.msi`.  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     Este comando quita el [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)] desde el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación.  
  
     Al proporcionar valores diferentes para la `REMOVE` propiedad, puede quitar los componentes específicos de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación. Hacer referencia a la tabla de **instalar en modo silencioso** en [instalar BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) para obtener información acerca de los valores que puede usar para esta propiedad.  
  
     Para quitar completamente el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], ejecute el comando siguiente:  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     Para obtener más información sobre el tipo de comando msiexec `msiexec` en la línea de comandos y presione `ENTER`. O vaya a [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).
  
## <a name="remove-the-bindings"></a>Quitar los enlaces  
 Siga estos pasos *sólo* si se produce un error en el Asistente para la instalación quitar los enlaces del adaptador o el registro del proveedor de datos de .NET Framework desde el archivo machine.config.  
  
1.  Vaya al archivo machine.config en el equipo. Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config  *\<unidad del sistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG*.  
  
2.  Abra el archivo con un editor de texto.  
  
3.  Quitar el registro de enlace del adaptador:  
  
    1.  Busque la `system.serviceModel` elemento y quitar lo siguiente en el elemento:  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  Busque la `bindingElementExtensions` elemento bajo system.serviceModel\extensions.  
  
    3.  Quitar las siguientes secciones en el `bindingElementExtensions` nodo, dependiendo del enlace del adaptador disponible. Si el Asistente para la instalación no puede quitar cualquiera, debe quitar todos los enlaces.  
  
         Para [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], quitar:  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], quitar:  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], quitar:  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], quitar:  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], quitar:  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  Busque la `bindingExtensions` elemento bajo system.serviceModel\extensions.  
  
    5.  Quitar las siguientes secciones en el `bindingExtensions` nodo, dependiendo del enlace del adaptador disponible. Si el Asistente para la instalación no puede quitar cualquiera, debe quitar todos los enlaces.  
  
         Para [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], quitar:  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], quitar:  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], quitar:  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], quitar:  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], quitar:  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  Quitar el registro del proveedor de datos de .NET Framework:  
  
    -   Busque la `DbProviderFactories` elemento bajo el nodo system.data.  
  
    -   Busque los proveedores de datos de .NET Framework que todavía están registrados. Quitar las siguientes secciones en el `DbProviderFactories` nodo, en función de los proveedores de datos existente de .NET Framework. Si existen, debe quitar todos los proveedores.  
  
         Para [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], quitar:  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         Para [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], quitar:  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  Guarde y cierre el archivo machine.config.  
  
## <a name="remove-the-custom-rfcs"></a>Quitar las RFC personalizadas  
Complete este paso para quitar las RFC personalizadas que ha instalado en el sistema SAP. Vea [instalar o quitar las solicitudes de cambio personalizadas](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).  
  
