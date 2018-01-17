---
title: Archivo de registro del adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6750f0ed-4411-4a63-a7fe-f66132cd1e22
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c38d00cbaf5d34aa880f5efd1d9e9a59d59c4e0
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="adapter-registration-file"></a>Archivo de registro del adaptador
Después de que el código del adaptador personalizado se haya generado correctamente, se debe registrar con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para ello, actualice el Registro con la configuración del adaptador adecuada. Puede escribir de forma manual un archivo de Registro, pero hay más probabilidad de errores debido a la precisión y complejidad de la información que hay que escribir. Una decisión más acertada consiste en ejecutar el Asistente para el Registro del adaptador. Este asistente le proporciona las mismas opciones de que dispone al crear un archivo de Registro nuevo y reduce la probabilidad de errores en el archivo. Para obtener más información acerca del Asistente para registro de adaptador, vea [Asistente para registro del adaptador](../core/adapter-registry-wizard.md).  
  
 El archivo StaticAdapterManagement.reg y dynamicadaptermanagement.reg se encuentran en  *\<unidad\>*: \Program Server\SDK\Samples\AdaptersDevelopment\File el adaptador de BizTalk. Al ejecutar uno de estos archivos (puede hacer doble clic o haga clic en y y seleccione **mezcla**), que registra el adaptador de archivo de ejemplo con el registro y se instala el ensamblado en la caché global de ensamblados. Para registrar el adaptador personalizado, la mejor opción consiste en crear un archivo de Registro nuevo mediante el Asistente para el Registro del adaptador. Si el adaptador estático personalizado es parecido al adaptador de ejemplo y decide modificar el archivo de Registro existente, abra y modifique las propiedades siguientes en el archivo StaticAdapterManagement.reg:  
  
-   **Restricciones**  
  
-   **InboundTypeName**  
  
-   **InboundAssemblyPath**  
  
-   **OutboundTypeName**  
  
-   **OutboundAssemblyPath**  
  
-   **AdapterMgmtTypeName**  
  
-   **AdapterMgmtAssemblyPath**  
  
-   **PropertyNameSpace**  
  
> [!NOTE]
>  Para **OutboundAssemblyPath** y **AdapterMgmtAssemblyPath** se recomienda que no incluya la ruta de acceso local en el valor de propiedad, porque la configuración podría dañarse cuando está instalado en diferentes ubicaciones de servidor. Una opción mejor consiste en utilizar un nombre seguro e instalarlo en la caché de ensamblados global.  
  
 Para especificar el tipo .NET que implementa el receptor del adaptador, el transmisor del adaptador y la administración del adaptador, existen dos opciones:  
  
1.  Instalar el adaptador en una carpeta y especifique * TypeName y \*AssemblyPath donde \*TypeName es un tipo. FullName de la clase y \*AssemblyPath es la ruta de acceso y el nombre del ensamblado.  
  
2.  Instalar el adaptador en la caché global de ensamblados y especificar sólo * TypeName donde \*TypeName es un tipo. AssemblyQualifiedName de la clase. Ésta es la opción recomendada.  
  
 Todos los adaptadores deben tener las claves de Registro siguientes con el GUID especificado:  
  
-   **Implementa categorías\\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}**  
  
-   **"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"**  
  
-   **"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"**  
  
-   **"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"**  
  
-   **"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"**  
  
 Los adaptadores basados en el marco de trabajo de adaptadores deben utilizar estos GUID específicos para las páginas de propiedades de ubicación y controlador de envío y recepción. Tenga en cuenta que si un adaptador es un adaptador sólo de envío solo necesita la **OutboundProtocol_PageProv**y **TransmitLocation_PageProv**GUID. De forma similar un adaptador sólo de recepción simplemente requiere la **InboundProtocol_PageProv** y **ReceiveLocation_PageProv** GUID.  
  
 El siguiente código pertenece al archivo StaticAdapterManagement.reg y el código del archivo DynamicAdapterManagement.reg es casi idéntico. Para obtener más información sobre cada una de las propiedades del registro, consulte [registrar un adaptador](../core/registering-an-adapter.md). Después de realizar cambios en el archivo de Registro, guárdelo y ejecútelo.  
  
```  
Windows Registry Editor Version 5.00  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}]  
@="Static DotNetFile Adapter"  
"AppID"="{12A6EBAA-CF68-4B58-B36E-A5A19B22C04E}"  
  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\BizTalk]  
@="BizTalk"  
"TransportType"="Static DotNetFile"  
"Constraints"=dword:00003C0b  
  
"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"  
"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"  
"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"  
"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"  
  
"InboundEngineCLSID"="{3D4B599E-2202-4bbb-9FC6-7ACA3906E5DE}"  
"InboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileReceiver""InboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll"  
"OutboundEngineCLSID"="{024DB758-AAF9-415e-A121-4AC245DD49EC}"  
"OutboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileTransmitter""OutboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll""AdapterMgmtTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.Designtime.StaticAdapterManagement""AdapterMgmtAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Design Time\\Adapter Management\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Designtime.dll""PropertyNameSpace"="http://schemas.microsoft.com/BizTalk/2003/SDK_Samples/Messaging/Transports/dotnetfile-properties"  
"AliasesXML"="<AdapterAliasList><AdapterAlias>DotNetFILE://</AdapterAlias></AdapterAliasList>"  
"ReceiveHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"ReceiveLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories]  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}]  
```  
  
### <a name="to-register-the-static-sample-adapter"></a>Para registrar el adaptador estático de ejemplo  
  
1.  Complete el siguiente procedimiento para ejecutar el adaptador de archivo de ejemplo del SDK. Para obtener más información, consulte [adaptador de archivo (ejemplo de BizTalk Server)](../core/file-adapter-biztalk-server-sample.md).  
  
2.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **Explorador de Windows**.  
  
3.  Vaya a la unidad de instalación de BizTalk Server y, a continuación, vaya a  **<**  `drive` **>: \Program** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\SDK\Samples Adaptador \AdaptersUsage\File**.  
  
4.  Para agregar el adaptador de ejemplo en el registro, haga doble clic en **StaticAdapterManagement.reg**. (Si desea agregar el adaptador de archivo dinámico al registro, ejecute **DynamicAdapterManagement.reg** en su lugar y usar ese archivo según corresponda.)  
  
    > [!NOTE]
    >  Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se ha instalado en la unidad C del equipo, debe modificar el archivo StaticAdapterManagement.reg con la ruta de instalación adecuada. Busque el archivo C: y reemplazarla con la unidad de instalación correcta.  
  
5.  En el **Editor del registro** cuadro de diálogo, haga clic en **Sí** para agregar el adaptador de ejemplo en el registro y, a continuación, haga clic en **Aceptar** para cerrar el cuadro de diálogo, comprobar que la información no era Agrega el registro.  
  
6.  Para cerrar el Explorador de Windows, en la **archivo** menú, haga clic en **cerrar**.  
  
     Ahora el adaptador estático de ejemplo estará registrado con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].